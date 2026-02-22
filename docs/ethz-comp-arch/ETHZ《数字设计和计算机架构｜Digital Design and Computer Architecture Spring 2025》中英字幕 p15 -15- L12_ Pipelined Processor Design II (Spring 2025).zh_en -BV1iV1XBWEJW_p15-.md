# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p15 -15- L12_ Pipelined Processor Design II (Spring 2025).zh_en -BV1iV1XBWEJW_p15-

![](img/1cd3d778f057152b7fcc509fdddc6cba_0.png)

。好。とい。なは。我个。O。は。嗯。かすごい。有好。有可能。Oh。然要。不。你们这样。这个问题。不好。そますね。啊。己八。た。然后。将是关内。I。るは。自以在他对讲。どさん。啊水。Okay。Okay。

不是。や。个。で。他这。家。他们这好视。唔使。我。そ什。Oh。Yeah。我起来。后。没说太少。Yeah。Yeah。啊。啊。中莞的。一ち？对。喂。好好。So。そ。系。你啲。Okay。然。あ好ら。啊。

这什么什么况。でで。这 is。来时候。暂し。有咩时候。切换。Its。出嚟。あす。🎼Yes。こ。Okay， let's get started， is this good。

 can people hear me？Okay。Okay， today we're going to finish hopefully pipeline processor design。

 not all the aspects of it because we're going to continue issues with pipelineing next week。

 but hopefully the basics of pipeline processor design。

 data dependence handling and control dependence handling will be clear by the end of today。Oh。ok。

So this is I think， your last reminder for this or you， which is due April 1st。

 which is before our next lecture。Okay， and this is what we're covering。

 we have covered multicycle micro architectureiture and we started building a pipeline after that and now we're going to cover some issues in pipelineing。

😊，And these are some of your readings， and I'd recommend doing these readings actually。

 they're relatively short and they explain the concepts nicely。😊，Especially the H&H readings。

 which we have covered in lecture last time， if you remember。😊，Okay。

 just to jog your memory this was our multie MIPS processor and this was our finiteate machine。

 we built this most of it at least and we said that we can easily handle multicycle memory access this will come up again in pipeing so don't forget these issues these are fundamental issues。

😊，And we asked the question， can we do better？And he basically said， oh。

 we can actually have different instructions in different stages。In this case。

 four instructions in four different stages， but you could have。

 we actually built a five stage pipeline as I'm going to show you soon。😊，Of course。

 we said we need to be more careful than this， we need to add pipeline registers， et ceter， right？

So essentially pipelining is doing multiple instructions concurrently at different stages of execution in a single machine。

😊，And we contrast it with multicycle and you see that we improve throughput significantly compared to multicycle processors later if you have time today。

 we're going to do some more performance analysis a little bit more carefully than what we've done over here and we'll see that pipelineing actually improves throughput but maybe not as 4 x over here here with four stageage pipelinelining over here PhD code execute right back these are the stages you get 4x improvement in throughput but life is not that beautiful as we will see today we're going to cover those issues today especially but before that let me cover a little bit more about how we actually design the pipeline we actually started with a single cycle my architecture。

😊，So that's the beauty of single cycle micro architectureitecture I said yesterday it was there。

 we discussed it for educational purposes we designed a single cycle micro architectureitecture a few lectures ago and this is something hopefully you remember there are no internal micro architectitectural registers over here as you can see right everything happens in a single cycle for every instruction and you know this we designed the data path for it and then we designed the control logic for it and we went through the exercise of actually which control logic which control signals should be asserted for which instruction right okay so this was designed there's no magic right？

😊，So how do you do a pipeline design basically if you want to design a pipeline processor。

 you go through the same process that we have gone through for both single cycle and multicycle you need to design the data path first and then you need to design the control logic later okay that's what we've done for every processor that we have designed so far。

😡，So a pipeline data path design， what is a pipeline data path essentially you start with a single cycle data path before you design the single cycleic data path。

 let's start with that。😡，And then。You decide how to break it down into stages。

And we decided to break it down into five stages， if you remember yesterday， fetch， decode， execute。

 memory access right back we're going to keep that five stage pipeline。

It doesn't need to be five stages， someone could decide to break it down into four stages。😡。

eight stages， 20 stages， some existing process actually close to 30 stages。

 so the goal is to really break it down into different stages so that you improve the clock frequency right that's the goal。

😡，So once you decided how to break it down into stages and there's actually a lot of science in this area that we're not going to go through exactly how you do it。

 that's not the subject of this course， assume that we've broken it down into stages。😡。

We add pipeline registers so that you can separate the stages from one another。😡。

You need to add pipeline register so that the thing that's done in one stage。

 in one cycle doesn't affect。What happens in another stage at the same cycle， right？

So each stage has a pipeline register that's the output of it。

 which is the input of the next stage and。😡，During the clock cycle。

 you do some processing in that stage。And the contents of the register doesn't change。

Only at the end of the clock cycle at the rising clock edge， if you remember。

 we update the contents of the pipeline registers such that。

The instruction in the previous stage finishes the previous stage and moves to the next stage does that makes sense our goal is to basically keep pressing instructions。

 keep moving instructions from stage to stage and every cycle you do something each stage at the end of the clock cycle you finish what you're done latch it at the end at the pipeline register at the end of the stage and the next cycle will be will start with what you have latched in the previous cycle to the register okay so these are that's the purpose of the pipeline registers I'm going to show you again pictorially this thing。

😡，Okay， once you add the pipeline registers， you need to propagate the data signals right and data signals。

 we already have a data path。 Data signals are clearly propagating because we designed the single cycle data path。

 but now。😡，You need to decide where those data signals need to go。

Not all data signals are needed by every stage。😡，And whenever you have data signals available。

 they are not necessarily needed in the next stage。

 they may be needed in the next next next stage right so you need to propagate those data signals to the appropriate stage。

 which means that you need to store those data signals in the pipeline registers okay and we've seen that also I'm going to show to you again。

😡，And also， on top of this， you need to make sure correct action is done in the correct stage。😡。

What do I mean by this， you need to ensure that the data signals go to the right place。😡。

You cannot basically send the data signal to the wrong place and we're going to look at that basically this is actually true for control signals also because control signals are part of the design of the data path。

 not the control logic necessarily， but essentially whenever a wire crosses stage boundaries。

 for example， when we're writing the ALU result to the register file。😡。

There's a control signal that says you need to write to the register file that control signal should be generated in the right state。

😊，Meaning the instruction that's in the right backst should be able to write。

To the register file and not the instruction somewhere else Okay。

 this will be also more clear when we actually go through the design。😊，Okay。

 once we design the data path correctly， hopefully you need to design the pipeline control logic and we already said control signals are essentially the same as a single cycle。

 so that's the beauty of single cycle you have the control signals and have the control logic that works for pipeing also。

😊，Not quite because pipelining does multiple instructions concurrently。

 which means that when you generate the control signals。

 you need to propagate them to the stages where the control signals are needed for every control signal you need to make a decision。

 this is the stage when I actually need that control signal and to be able to propagate that let's assume that you generate the control signal in the decode stage。

😡，This is one of the options that we discussed yesterday I'm not going to go through the options again。

 you don't need it in the next stage which is the execute stage。

 but you need it in the memory stage or right back stage you to propagate those control signals in the pipeline registers okay then the goal is to make sure that the control signal travels with the instruction such that you take action or you take the right action at the right time based on the partitioning that you've done for the pipeline。

😊，Okay， so you need to extend the pipeline registers to do so and I've given you a picture of that。

 I'm going to show you again。Okay， is this all clear， yes， why don't we use motorcycle？审查。Okay。

 what would be the benefit of that。The job frequency still have that benefit Okay。

 but how would you like combine both of them so multicycl goal is to really in a sense in the multi cyclee。

Okay， in pipeing you're really multicycle right each instruction is really multicycle Piing by itself is a multicycle paradigm right each instruction is going through five stages。

 for example， our five stage pipeline。😊，So it's by itself multicycle， does that make sense？嗯。Okay。

 good。Okay good questions though I mean you guys should think and the thinking is good that makes you ask questions like this and actually there's a combination but I'm not going to go into that combination right now that's a different kind of combination okay so let's go through what I just said I went through this yesterday but I'll go through it a little bit more today but this is our single cycle processor it's really the data path mostly one version of it but we built it earlier you remember we have the instruction memory over here register file ALU data memory and the writing back action over here and we basically first need to divide this into stages right that's the first thing you need to do。

😊，Let's assume that we decided the first day should be the fetch。

The second stage should be a register file read decode and control signal generation which I'm going to show later the third stage should be ALU execute essentially the fourth stage should be memory access the last stage should be right back so that's what the stages each instruction goes through and each instruction does fetch here decode here that's why its called ifFI and then execute here memory access here and write back here so if we don't write back data from anywhere else but the right back stage into the register file makes sense we write to memory in the memory stage that's a different right but we write to the register file in the right backt okay and every instruction goes through these stages so by definition is a multicycle thing but every instruction is going through the same stages。

Okay， so we also added by once we divided our single cycle data path into five pieces。

 let's say we also added these pipeline registers， as you can see。

 these are registers that are going to store both data signals as well as control signals。😊。

Let's take a look at the sum of the data signals， these may not be all of the data signals。

 but for example here after you fetch you store the instruction bits。

We called it the instruction register in the past， so you can think of a part of the pipeline register storing the instruction register。

 right？We also store PC plus four because we're actually going to need it in address calculation as you can see so any data signal that you're going to need later on for the execution of the instruction。

 you should really propagate down the registers So in the first cycle you fetch this instruction in the next cycle you decode。

😊，In the decode stage， this PC plus4 gets propagated directly to the next register because you don't use it here。

 we're going to use it later on actually， but you don't use it currently here。

 but you'll use it in the next stage， which is the execute stage for some things like branches。

 right？😡，And also， we read the register file and we store the outputs of the registers。

 essentially the data values of the two registers that are read。

 and we also store the sign extend immediate。😊，And these are going to be needed for execution of different instructions over here in the next stage okay so I could keep doing this essentially here you calculate the next PC based on PC plus4 and signex and immediate left shifted and then you store it at the end of the execute stage and the execute to member registers execute slash stage registers AL output is also stored over here and look at there's curiously something called B over here。

😊，What is that be， the speed is really the register， the second register that you have read。

 so we directly propag it from the execute stage input register。

 IDEX register to execute the memory register without changing it because it's needed for stores。😡。

Whenever you're storing， you need to actually take the data from the register file and write it in the memory right so you propagate all of the data signals that's needed across the pipeline stages。

 Yes， not problematic that thiss in the goes back register。😡，So is it not problematic this mugx。

 it's not actually。I think it was back into the registry without there might be something else in the。

That's true， so we'll look going and talk about that。

If that something else is not reading that register it's not problematic so what does this mugs do let's take a look at it this mus is or this this wire yes you should always be careful with these wires the goal of this wire is to really write the data into the register file。

😡，And you write the data from this instruction over here， right？

So the instruction once an instruction reaches the right backstage。

 if it's writing to the register file， it writes the data， if it's a load。

 you write the data that is latched in the previous cycle while the load was in the previous stage from memory。

 if it's an ALU operation， then you latch you write the data that is the result of the ALU right as we have seen in the single cycle data path actually。

😡，So basically you should be writing the data， no question about that。

 this is not problematic as long as nobody else is reading the data， right？😡。

Does that make sense as long as there's no other instruction previously？😡。

That there's no other instruction in the previous stages of the pipeline。

 meaning there is no other younger instruction。😡，Then you can write that data without problem right and we're going to get to this。

 we're going to cover all of these issues， okay。😡，Okay。Okay， so hopefully it's clear。

 So now we went through almost the entire pipeline， and this is how you construct the data。

And you need to ensure that no resource is used by more than one stage， so here， for example。

 when we'mre writing the data over here， this right port is not used by anyone else。😡。

Only this register。 now， well sorry， only this instruction the right backstage。

Now this becomes problematic if someone else is trying to read that register， right？

Or if there's another instruction that's over here that should have already read that register。

 Think about it。 We're fast forwarding a little bit。But so far。

 we're kind of assuming an ideal pipeline。Okay。So control points in the pipeline this is essentially our single cycle pipeline processor that we just designed it's the same thing with a slightly different view with some control points added so this was a data path design now I added the control points over here so control points are essentially the same as what we did with single cycle if you remember the single cycle processor we had a red rightite signal we had some other signals over here to make sure the instructions execute properly we have exactly the same signals。

😊，Nothing has changed over here。😡，You still need to generate the control signals and that control logic is essentially also the same。

 you still have the same control unit over here based on the instruction register。😡。

The major difference is you delay the control to the proper pipeline stage， right？So for example。

 when you're in this stage。You're not writing to a register。

 the instruction in this stage is actually reading from registers right so the control signal。😡。

Rg Wright should not be coming from the instruction in this stage。

 the control signal red Wright should be coming from the instruction。In this stage。

 because that's the only stage where an instruction can write to a register， okay。

 which means that when you generate the control signal。When you decode the instruction。

 you figure out， oh， this instruction right registers or a write should be set。😡。

You place that control signal into this pipeline register。And propagate it。

And use it when it's really needed。😡，Makes sense， so you can see that this signal over here is the red right signal。

And it's used only it's connected to this pipeline register over here。

 which is the right back pipeline Reg， which says that the instruction in the right backt is supposed to write to the register file。

😡，Because that control unit， when it decoded the instruction three cycles ago。

 it set that signal appropriately， hopefully because it's an instruction that tries to register。

So we're going to connect that register， that control signal in that register into the redrite signal of the register file。

😡，Makes sense okay similarly， we need to propagate the signals that are needed in the memory stage so we generate well this control you know generate some signals that are needed in the memory stage。

 especially important for memory instructions but for other instructions also other instructions should do no harm to memory let's say and when an instruction reaches the memory stage。

 it takes the appropriate signals that are needed in the memory stage and uses them for example。

 if it says store instruction， memory right signals should be set， memory signals should not be set。

😡，And as a result， we write the address coming from this pipeline register。

 which was calculated in the previous cycle， previous stage through the ALU。

 we write to that address， the data that's coming from this register。

 which was latched directly from this register in the previous cycle。

 which was read from the second port of the register file。

Hopefully this all makes sense right the instructions are moving in the pipeline and need to move the control signals appropriately as well。

 yes。😡，We one block like for example， if reading takes longer than okay， I'll say patience again。

 sorry， very good though essentially you guys that are thinking ahead。😊，So if there's something。

 for example， if the memory takes more than one cycle， right， that's what you're saying。😡。

Essentially this pipeline currently doesn't handle that but we're going to talk about how to handle that essentially okay let me answer the question if we are assuming everything is moving so the assumption right now we make is everything is moving you keep the pipeline always moving there's always instructions coming in they keep going through without any trouble right the pipeline is flowing in other words if something blocks the pipeline or stalls the pipeline we're going to call the stall you need to stop the pipeline。

😡，Meaning this instruction here is accessing data memory it takes。5 cycles。

 meaning that this instruction cannot move anymore。 What do you need to do。

 You need to make sure nobody moves， nobody previously nobody in the previous parts moves This instruction over here doesn't move。

 This instruction doesn't over here doesn't move。 This instruction over you here doesn't move。

 And what happens here。😡，This instruction cannot move to the next stage so you actually insert and no up no operation you kind of basically insert a bubble but we will get to that that's a very good question and this is this is going to be our strategy for handling any kind of blocking or stalling whether it's because a long latency operation or it's because of a dependence as we will see so。

😡，Okay， so I've already discussed this compulsing。 So hopefully it's clear。

 This is actually where we left off yesterday， but I want to discuss things a little bit more so that hopefully everything' is a little more clear right now。

😊，Any questions， thoughts？Okay， now that we've covered some of the basics let's go through another pipeline over here a little bit more basics This is what your book developed actually your book is also very nice in pipelineing it's chapter 7。

5 if you're interested in reading it it does essentially the same thing I did this is the single cycle processor that your book developed。

😊，And it basically breaks it down into five stages， fetch thecode， execute memory right back。

 as you can see。😡，And its add pipeline registers。And it has this instruction part。

 you can see that there's the right drag signal over here。😊，And we ask the question， is this correct？

So basically assuming an instruction is supposed to write back to a register file over here。😡。

Because the data value is available only after here。

 right for memory instructions for ALU instructions is really available over here。

 writing the data value into register file here is wrong right because you' would be writing the wrong data value。

Which is coming from here。So the control signal over here is coming from this instruction。

 whereas the data signal is coming from this instruction， and you should never do that。

If you're writing some data， assuming it's writing it at the appropriate stage you should use the control signal at the appropriate stage。

 so basically this is how you fix the problem， you propagate the right right signal over here and you that right tick signal from the right back stage essentially the control signal must arrive at the same time as the data signal okay。

😡，And this is all based on the semantics of the instruction clearly， right。

 if you're actually using a control signal that belongs to some other instruction， it makes no sense。

😡，Because we've divided the machine into five different instructions。

 You should use the control signals that you propagated for the right instruction。 Okay。

 I think I've heart on this enough。So this is the pipeline control that your book develops。

 it's essentially the same as single cycle processors control unit and control is delayed to the proper stage and again I would recommend that you take a look at your book。

😊，Okay， so basically， we've covered howo to design the pipeline data path and control logic。😡。

Now the question is this sufficient and as multiple of your colleagues already kind of hinted at。

 this is not sufficient。Basically there are two major questions。

 at least two major questions I'm going to expand this。

 how do you handle dependent instructions if an instruction that comes later in the pipeline is dependent on a previous instruction。

 for example you have a load instruction load instruction goes here in the pipeline。😊。

And add instructions depend on it Can the a instruction be here while the load instruction is over here？

😡，And the answer is no， because load instruction did not generate its result yet。😡。

Ad needs that result， so ad cannot be computing。😡，Anything。If if it didn't get that result yet。

 right that's the idea， so you cannot keep the pipeline moving。

 you need to stop the pipeline when you detect a dependence between instructions。😡。

And as you have also mentioned， if theres like multicycle memory access， it's a similar issue。

 you need to stop the pipeline， we're going to talk about that。

 but there are other issues so I'm going to talk a little bit more about this ideal pipeline you've seen the slide before essentially an ideal pipeline requires identical operations。

 same operations repeated independent operations。😊，There should not be an ad depending on a load。

And uniformly partitionable solvebar patients， basically you can divide everything uniformly to solvebar patients Unfortunately。

 an instruction pipeline violates all of these。😊，You don't have identical operations。

 you have different instructions， not all of them need the same stages and we are forcing different instructions to go through the same pipeline stages now this is not a bad evil。

 let's say we're going to also fix this a little bit when we talk about multicycle execution。😡。

Next week， but it's caused external fragmentation， meaning some pipe stages are ideal for some instructions and we saw that yesterday right an R type ALU instruction an add instruction goes to the memory stage and it does nothing in the memory stage right。

😡，Okay， so over you've seen this， that's called external fragmentation。😡，Okay。

 there's also uniform sub patients， let me cover that first different pipeline stages are really not the same latency yeah。

 and we also talked about this yesterday。😊，But you have to force each state to be controlled by the same clock。

😡，And as a result， you have some internal fragmentation in the clock。

 which means some pipe stages are fast but still have to take the same clock cycle time。😡。

So you lose some performance from there also， okay？

And now let's get to the independent operations part。

 which will essentially consume quite a bit of our time in this lecture and the next lecture and the next lecture as well。

 essentially the a huge problem is instructions are not independent of each other right this is not like the laundry loads。

😊，Laundry loads are independent of each other there's no dependence between my laundry and your laundry and your laundry or something like that right or my different laries I can mix and match also。

😡，All right， so basically you need to detect and resolve inter instruction dependences to ensure the pipeline provides correct results。

😊，So our pipeline that we built is not correct yet。

It is correct under some conditions where instructions are all independent of each other and memory is one cycle。

😡，Quick， there is no stalling condition， basically。So basically， this leads to pipeline stalls。

 meaning pipeline is not always moving。😡，There will be conditions under which the pipeline stops。

Okay， this brings us to a lot of exciting issues in pipeline design that has enabled a lot of creativity and creative solutions。

 and we're going to see a lot of these creative solutions。

So balancing work in pipeline stages that's not something we're going to see how many stages and what is done in each stage。

 this is still an issue， it's always an issue， but it needs to be dealt with。😊。

So this is the part that's really interesting and exciting， I think。

 and this will be this will enable us to build up to auto order execution。😊。

So we want to keep the pipeline correct， moving and full， and we want all of them actually。

 these are actually， if you think about it， these are different things。

 but all of them together makes the pipeline good。In the presence of events that to disrupt the pipeline flow。

So what are those events that disrupt the pipelineflow， data and control dependencies。

 we're going to spend a lot of time on these。😡，Resource contention。

If two things need the same resource at the same time， what do you do？Handling long latency。

 multie operations like long latency， memory accesses， long latency instructions。

 and multiply maybe longer latency than an ad， for example， how do you handle that， right？

And then handling exceptional conditions like or where a problem happens in instruction execution。

 you divide an instruction， you have a divide instruction and you divide by zero。😊。

That's an exceptional condition， what do you do， right？

What happens when an interrupt comes in and interrupts a process。

 we're going to talk about that next week。So basically。

 we want to improve pipeline through good by minimizing stalls。

 but let's talk about these stalls first， how do we actually handle stalls。😡。

So what are the cause of pipeline stalls， so what's the stall essentially as I kind of defined it earlier。

 but more formally it's a condition when the pipeline stops moving or it should stop moving if you keep it correct。

😡，Right。So there are three major cause of stalls， one is resource contention。

 I'm going to quickly talk about it， but we're not going to develop it that much。😡。

The second one is dependencies， we're going to talk a lot about that。

 these are dependencies between instructions， data dependencies where an instruction needs the result of another。

 and control depends where an instruction is the fact that you need to fetch an instruction is dependent on the fact that you fetch and executed a previous instruction。

Okay， and then there's a long lengthonency multicycl operations。Okay。

 dependencies are also called dependencies or your book calls it less desirably hazard。

 hazard is a very alarming term think I think it's just a dependence。

 basically you have essentially these are there because you need to have ordering requirements between instructions。

 right？If an instruction needs the value of another instruction， there is clearly a dependence。

 flow dependence between those two instructions。So there are two types of dependencies。

 data dependencies and control dependencies。Resource contention is sometimes called resource dependence。

 I think this is correct。 actually， you're dependent on the same resource。 It's not like a hazard。😡。

But it's a very different form of dependence， it's not inherent in the semantics of the program。

 right？😡，It's basically a hardware dependence。😡，So it's really not fundamental to the program semantic。

 so we will treat this separately。 In fact， that's what I will treat first。

So let's talk about handling resource contention this happens a lot when you design a pipeline it happens when instructions in two pipeline stages need the same resource。

 so whenever you're design the data path you need to be careful about it also the control logic of course so how do you actually handle this first eliminate the cause of the contention right？

😊，Basically replicate the resource。 We kind of did this with the dryer， right。

 earlier so that we could keep the pipeline moving。 We actually had two dryers。

Duplicate the resource or increase the throughput。😡，Use separate instruction and data memories。

 for example， caches， as we will see， or use multiple ports for memory structures。 This is obvious。

 hopefully。😡，The second solution could be， okay， I don't have enough， let's say。

 money to replicate my resources， so I'm going to use a single resource but detect the resource contention and stall one of the contending stages。

That's also possible， right？This we're going to of course add the stalling logic later on。

 but it's possible to handle this way the question is which stage do you stall for example。

 what if you add a single read and write port for the register file and an instruction in the right back stage needs to write to the register file and an instruction in the read stage or register read stage needs to read from the register file。

😊，Clearly， you should stall the instruction that needs to read， right because。😡，You need to meet。

 you need to keep the pipeline moving。😡，The older instruction is the instruction that needs to write to the register。

 and it should once it writes to the register it'll get out of the pipeline， right？😡。

So prioritize that instruction and make sure it writes to the register file first using the single port that you have。

😡，And other instruction will read from that same port later on in another cycle， for example。

 so I need to add control logic to detect these things。

Okay there's one trick that your book assumes and a lot of books actually assume also which may or may not be realistic and depend on the design。

 I'm going to tell you that trick， so with careful design the register file can be read and written in the same cycle I will not go through exactly how this is done but you can essentially a register file right takes place during the first half of the cycle you can design the register file to be that way and register file read takes place during the second half of the cycle。

😊，Okay。This way you kind of handle this resource contention that I kind of talked about。

 right at least this particular one。So a read or write from and to the register file has only half a clock cycle to complete。

😡，Now， if you do this， there is one benefit， let's take a look at these instructions。

 these instructions are not really ideal， but for example。

 this instruction writes to register too in the first half of the fifth cycle。😡，Now。

 if another instruction needs register too。😡，They can do it in the second half of the fifth cycle okay。

 this is our pipeline load inspection first cycle in the fetch stage。

 second cycle in the decode stage， third cycle and the address generate AL stage fourth cycle。

 the memory stage fifth cycle it write to the register file。In the cycle。

 first half of the clock cycle， or the fifth clock cycle， it does this writing。

And then you can see that the instructions are pipeline， if an instruction needs that register。

 it can read it in the second half of the fifth clock cycle。

 so this instruction can basically read from S2 in the second half without any problem。😊，Okay。😊。

Later instructions can， of course， read from the register file， right。 Yes。

 cash it's written basically， it's it's simply written。

 We're assuming that the structure of the register file。

Simply takes the value is written and at the same time。

The read puts it into the the other instruction it leads。So basically you have a register file。

 right， you have eight registers， let's say you're writing to register two。

 the right to register two completes within first half of the clock cycle。😊。

And anything that needs that reads that instruction in the same clock cycle will get the correct value in the second half。

Okay。😊，So the assumption is that you need only half of the clock cycle to right to the register okay。

 we're going to move patience， I like saying that to you sorry， but you're thinking ahead。

 yes you could also pass it directly。😊，We're going to see those direct passing， direct forwarding。

 we're going to call it forwarding。Okay， very good。 Okay， but this is a trick。

 This is actually a forwarding trick I would I call internal register file based forwarding。

 but this enables you to actually。😊，Do the right and health of the cycle and read in the second half。

Okay。Okay， let's talk about data dependenceencies now， but before I talk about data dependence。

 maybe in this figure I will illustrate something this instruction is writing to register to in the first half of the fifth cycle。

😡，If this instruction were dependent on that。😡，It cannot this pipeline cannot be moving like this。

 right？This instruction needs to wait until it can read the value from the register file。

Or somewhere else， as we may get to later。Okay， so let's talk about these data dependencies。

 so there are three types of data dependencies， one of them is real the other two are fake。😊。

The real one is flow dependence， it's also called true data dependence， read after write dependence。

😡，This is where an instruction is writing to a register and then later instruction reads from that register。

 so you truly have an data dependence between the producer of the register and the consumer of the register。

😡，And then we have anti dependence and output dependencies， are not these are fake。😡。

But they still affect the pipeline， depends on how you do the dependence checking， et ceter。

 essentially we need to be careful about them still。

 and we're going to actually illuminate them when we talk about auto order execution。😊。

So which one causes stall in a pipeline machine， essentially for all of them we need to ensure cement so the program is correct。

 I'm going to show you the anti and output dependence with a pictorial example suit。😡。

Flow dependences always need to be obeyed because they constitute true dependence on a value。

 right you communicate values between instructions。😡。

Andti output depends exist due to a limited number of architectural registers， for example。

 anti dependence or output dependence means right after write an instruction is writing to register5 and later instruction is also writing to register5。

😡，These may have no relationship with each other， they are just names dependence on a name。

 which is Reg five， right？😡，You don't have enough architectural registers so compiler allocate register five to both instructions。

😡，Okay， so that's what I mean by it depends on a name， not a value。

 this will become a lot more clear when we talk about register renaming and auto of order execution later on。

😡，So we will later see what we can do about that so let's take a look at these dependence types so flow dependence so these are our operations let's say it can be any operation over here。

😊，Pick your favorite operation， but the first one does something to register one and register two as towards the result to register three。

 the second operation that comes after this reads Reg three。😊，Which means that it's dependent。😡。

In a true manner to previous on the previous instruction and this is a true dependence because this register is really communicating a value produced by the first instruction to the second instruction that needs that value for computation right。

 this is absolutely necessary。😡，You could change the register three to register 1000 here if you have it。

 you have to change this to register 1000 also， right？😡，Does that make sense？

Because one instruction is producing the value， the other sector is consuming the value。

So you need to supply the value。From somewhere and the realization is that we're going to supply this value。

 not necessarily from the register file soon Okay， so antidependence it looks like this。

 the first instruction， the older instruction is reading from register one， the younger instruction。

 the next it happens to be the next instruction is reading from Reg one。😡，Oh， sorry， writing into。

Read write after read， there's a right that happens after I read to the same register。Now。

 if you think about this， these registers have the values stored inside the registers have nothing to do with each other。

 right？😡，There is some value in Reg one that's needed for the previous instruction。

 this instruction overwrites that value， it doesn't need register one。😡，So if you had more registers。

 let's say I have my favorite Reg 1000。😡，If I change the first one to register 1000。

 I don't need to do anything to this。😡，That way， I've eliminated that dependence。

 That's why this is not a true dependence， that's a false dependence， It's fate。😡。

The reason it's there is because we don't have enough registers and we're going to see this problem over and over。

 Why don't we have enough registers。😡，Because we cannot have a huge register file that's a one good answer。

 the other good answer is if you have thousands of registers or and codinging of the registers in the instructions set will be huge。

 so our instructions will be huge， right？😡，So there are multiple answers to this。Yes。

 even if we don't have enough registers， why is this a problem if we write to the register after we have read。

Okay， so why is this a problem， basically the problem is you need to still design the pipeline to make sure you don't get the wrong value。

😡，Okay， so this is one of the reasons why we write to register one at the end of the pipeline stage。

😡，Okay。But then we always write off the movie， right。Well。

 not necessarily if you have a pipeline processor， if you didn't design it correctly。

You might actually let's say this is the next instruction this somehow anyway this maybe this's not the best example。

 but it's possible to imagine that there will be some case where you could write to this register and this one incorrectly gets the value okay yeah。

😊，I cannot demonstrate it right now， but。Yes。😊，Okay。

 the output dependence is another example of fake dependence and here you see this instruction is writing to register3 and there's something that's happening。

 there's an instruction that's dependent on Reg 3。😊，And then this instruction is also writing three3。

3。And again， the realization is that if you had enough registers， you could rename this one。

 the bottom one are 1000。And nothing would have to change。

 and there would be no right after right pen。Okay， so basically you need to be careful with these anti- and output dependencies。

 they still consume some of your resources and also if you somehow you don't want to reorder the rights right。

 if you always write to register at the end of the pipeline when the instructions is the oldest then hopefully you will not run into any problems in terms of anti and output。

😊，But with flow， there's still a problem， you need to supply data out， okay。Okay。

 so this is our pipeline。Basically， let's see two instructions flowing over here。

 a load word and an independent sub。If it's independent， there's no problem， right？😡，Okay。

 everything writes back at the end， so basically the way to solve the anti and output dependencies is to make sure rights happen at the very end of the pipeline and in an in order manner。

 right？Okay。So what if sub were dependent on load word and that's what we're going to deal with right now and these are some readings actually these are these readings I already mentioned。

 but I'm going to also recommend this reading because it's going to be useful later on when we talk about interrupt and exception handling out of order execution superscale execution all of those we're going to cover and it also covers depends and their types and their handling in a nice way so I'd recommend you take a look at that。

😊，Okay， so anti and output depends are easier to handle。

 as you kind of guessed right to the destination only in the last stage and in program order。😊。

Flow depends are more interesting and challenging， and there are actually six fundamental ways of handling flow dependencies。

 we're going to cover some of them。😊，A lot of them require detection。

 you detect the flow dependence and you wait until the instruction that's producing the value writes the value into the register file。

 okay， detect and weight basically。😡，You detect the floor dependence。😊，And forward the data。

From the producer instruction to the consumer instruction。

 whenever the producer produces the instruction， you don't wait until the data is written to the register file。

 these are two different things as we will see。😡，You detect。

That there is a dependence and eliminate the dependence at the software level。

 so software figures out that two instructions are dependent on each other and I should separate them a little bit so that they don't cause problems to each other in the pipeline this is actually a very powerful technique if you can do it。

😊，And then you detect the dependence and move it out of the way it's going to be out of order execution。

 we're going to talk about that。😡，There's another approach which is predicting the value。

 which we're not going to cover， you say， oh， I have a dependence。I don't know what to do。

 but I'm going to guess。I think my value is going to be zero。

Right or based on some records I've keep kept in the past。

 which is going to be what we will do later in lectures 16， etc ceter， I'm going to guess。

 and you execute the instruction， but if you're wrong， you need to do something about it okay。

 you need to basically fix the problem Yes why do you want to move them why not get forward assuming you're forward。

 yes yeah， if you can forward， yes if you can forward， you can also try to move them closer。

 but moving them far apart to eliminate the dependence essentially。😊，In the pipeline。

 you don't need to do anything in the pipeline。Okay， yes。我认。I cannot hear you very about。 Go ahead。

 yes。😊，sThe problem。是没。not this one， it's a different prediction we'll talk about branch prediction later on。

😊，Okay， and then there's through something else， which is one of my favorite solutions。😊。

We're going to talk about that hopefully later today with fine grain multithing and the idea。

 let me give you the basic idea because all of these are actually creative and nice ideas that have each LED to a lot of different types of research。

 do something else means。Exece from a different thread that you know is independent。

So the next instruction comes from some other thread， some other execution context。

And you know that they're independent， so you don't need to do anything。😡，Right。Of course。

 there are upsides and downsides to this， modern GPUs do this， for example。

 and we will see that in later lectures。😡，Okay， so let's talk about this detection because a lot of these require detection。

 right how do you detect the dependence？😡，But before that let me show you the problem basically so this is a five stageage pipeline and I have these ads over here and the first ad is writing to register A and all of these other ads are kind of implicitly reading from not implicitly explicitly reading from Regtry A but I'm showing this as an example right so if you actually we're assuming that right happens at the end of the right backst we don't have this clever trick where you are able to write to the register file in the first half of the clock cycle right if you have that clever trick you can do a little bit better。

😡，But basically。If if this instruction this instruction comes into the pipeline is decoding。

 it needs to read the Reg A， if it reads Reg A at this point clearly there's a problem right it's going to read the wrong Reg A because this instruction write to register only at this point right similarly these instructions will get the wrong value also if you don't do something about it of course。

 only this instruction will get the right value right。😊，Makes sense。

And the later instruction will hopefully get the right value also。

So basically you need to do something about these instructions。

 you cannot just basically let them flow through the pipeline， right。😡，🎼Okay。

 so how do you do that so basically here let me finish this you have a right back this is instruction I in the general case。

 you have instruction I instruction I is writing to a register over here If in an instruction J is dependent as a flow dependence on instruction I。

😊，You need to separate them enough。😡，In the pipeline so that instruction J gets the correct value。

So what does that mean， basically instruction Jane needs to wait。

You detect that there's a dependence and make instruction J weight。

 what does that mean instruction J stalls， it stays in the decode stage one cycle， not enough。😡。

Because this instruction still hasn't written， finished writing to the register that instruction J needs。

 stole one more cycle， not enough。And then stole one more cycle， now it's enough。

So basically we insert bubbles in the pipeline。s instead of this instruction moving in the pipeline and no up moves in the pipeline。

 no operation moves in the pipeline， and you don't do anything clearly that instruction doesn't do anything。

 you're basically stalling。😡，And that's the idea of basically the idea of a stall is to make the dependent instruction wait until its source data values available。

 So what does it mean to stall， you stop all upstream stages upstream means。😡，Younger instructions。

Younger instructions stall stop and all of the older instructions get out of the pipeline right until the instruction that is actually causing the stall gets out of the pipeline。

 then you stop stolen。😡，O。This is a good place to take a break I think。

 and then we're going to talk about different ways of detecting as well as handling these data dependencies and hopefully we'll get to find grain multi threading as well。

😊，对。で。但。あ。他时间。そですか。对。おし？放好。你没。不在。嗰。还だ。Yeah。あですか？That。What。啊。て。我や。Thank。はは。系下你自。あ。这子。前完。そ。我。为。Okay。

Yes束。そか。Yeah。好说。中。对。That。恭行。No。对。Okay， everything is good online。Okay， let's get started。You。

So now we have defined pipeline stall if you know exactly what it means。

You make the dependent instruction wait until it source data values available right and to do so you stop all down upstream stages。

Meaning you stop all younger instructions， including fetch， so the program counter doesn't change。

 you basically are at the same instruction， same program counter at the fetch stage。

 same instruction you're decoding， same instruction you're executing wherever you are basically and you drain all the downstream stages so that the stall condition gets removed right？

You handle a long latency memory operationpat or long latency operationpat the same way。

If an instruction needs to wait in the memory stage， you wait。

 meaning stall all upstream stages and drain downstream stages。

 and whenever the memory returns the result， you move on okay so it's a very general way of handling disruptions in the pipeline。

Okay， so now let's talk about interlocking or detection of dependence。

 essentially interlocking is the detection of dependence between instructions and a pipeline processor to guarantee correct execution。

😊，And as we will see more and more in later lectures。😊。

There are ways of doing this in software and there are ways of doing this in hardware。

So there's software based interlocking， meaning software detects a dependence between different instructions and does something about it。

 reorders code for example， such that dependences are separated from each other such that they don't really cause a problem in the pipeline。

 software ensures that the pipeline is always correct， moving and full。😡，If it's possible。

 it's a difficult task， but as we will see there are ways of doing it and if you cannot do anything。

 you can insert no op instructions， no op or no operation instructions that don't do anything right clearly that's not good for performance right。

😊，Or you can do it hardware based hardware based meaning hardware detects the dependence between instructions in modern processors both are employed。

 we're going to talk about both， but we're going to especially look into hardware based soon。😡。

Does anybody know the longer version of the MIPS acronyms is the ISA that we've been dealing with？

I mean， you never。Said what it was。Anybody， it's not millions of instructions per second。Yeah。😊。

No one。I don't expect anyone to know this， but it's essentially it actually stands for microprosor without interlocking pipeline stages。

😊，So people who designed this instructions at architecture。

 their goal was to design a pipeline processor that's really simple。

And they designed the ISA based on this assumption。

 and they wanted this microplster to not have any interlocking pipeline stages。

 meaning hardware interlocking。A goal was to handle as much as possible in software。😡。

Now that didn't work out very well， the latest MIPS processors are all very heavily doing hardware interlocking。

 meaning hardware dependence detection， and we will see the reasons because that's better for performance。

😊，Okay， so there are two ways of detecting dependenceencies in hardware， ones scoreboarding。

 the other is combinational dependence logic check very quickly I'll go through these。

 but you can think about these on your own essentially scoreboarding means each register in the register file has a valid bit associated with it we're going to see this later on in automotive order execution also。

😡，In instruction， you're decoding an instruction， and whenever you're decoding an instruction。

 you figure out that this instruction is supposed to write to that register。😡。

It sets that well a bit at that point， sorry， it resets that well bit at that point。

 saying that this register value you cannot trust。Because I'm going to go through the pipeline and at some going at some point。

 I'm going to write to this register。 right， So for each register。

 you have some metadata saying whether you can trust the value in that register currently in the E stage or not。

In instructions， the decode state checks if all its source and destination registers are valid。😡。

So in the deco stage， whenever you're decoding instruction。

 the first thing you do is you check whether all your source and destination registers are valid。

 meaning you can trust the value， there's no one else in the later parts of the pipeline that are writing to this register。

😡，If that's the case， then you can continue， right there's no dependence。

But you reset your destination register。Okay， so this is how you detect dependence basically。

 if all of your destination registers are wed in the equal stage， when you read the register。

 when you read these we bitts， you don't need to stall， there is no dependence。😊，Otherwise。

 you stole the instruction。And of course， you need to make sure when an instruction actually writes to the register that it's supposed to write you set the value again。

 right correctly so that later instructions can continue Okay。

 so this's a very simple way of detecting dependence and stopping instructions。

That depend on instructions that are later in the pipeline that's going to write to a registergi。

The address is very simple， one bit for register， some people actually call these full empty bits。

 is the register full or empty， empty means somebody is going to write the value and it's not written yet。

😡，The disadvantage is， unfortunately， this requires you to stall for all types of dependencies。

 not only flow dependencies， and you can think about why is that the case？

There are ways of fixing that， but I'm not going to fix that this is just an idea I just want to give the idea of one way of doing it。

😊，Okay， so if you do that， what happens is in the instruction decocode stage， this load instruction。

 okay， let me go into the okay。Yeah。Okay something happened over here。

 but this load instruction is assumed that it's writing to register 10 it's going to set the it's going to reset the v bit of register 10 when the subtract comes here if it's reading from register 10。

 it'll see that the v bit is zero so it'll stop。😊，Meaning it will not go there is this stall condition in other words。

 this register， this subtract will stay here， this other instruction that's being fetched over there will stay here。

 load will move and there will be a bubble inserted here as we will see and then load will move again and once load actually finishes the right backstage it resets the valve bit to one。

😊，At that point， the subjecttract can move。Okay， so that's one way of doing it。A more aggressive way。

 which is a little bit more costly in hardware， is combinational dependence check logic。

 this is what's done in your book and in many books。😊。

There is a special logic that checks if any instruction in later stages is supposed to write to any source register of the instruction that is being decoded this's a mouthful but essentially it says whenever you're being decoded。

 you have some source registers， you check whether any of those source registers are going to be written to by any instruction that is in later stages in the pipeline。

😡，You can think of basically you compare there should be some comparators for each source register。

 you have a compator to the destination register of every instruction in later pipeline stages。

 right？😡，Okay， assuming those instructions are writing， of course， you need to check that also， okay？

So if the answer of that combinational dependence check logic is yes。😡，For a given source register。

 there is at least one instruction in later pipeline stages is writing to that register or that's going to produce the value of that register you stole the instruction and the pipeline otherwise there's no need to stall because there is no flow dependence。

So the advantage of this is there is no need to stall on anti and output dependencies。

 it's very clean， we just check for flow dependencies。😊。

The disadvantage is logic is more complex than a scoreboard。

And logic becomes actually more and more complex as your pipeline becomes deeper and deeper。

We have a very simple five stage pipeline here。If you make it 15 stages。

 but I need to check all of those stages downstream。😡，And actually， later。

 we're going to see something called superscalealar execution。

 The idea is not have a single pipeline。 The idea is to fetch multiple instructions in a given cycle。

 So replicate the pipeline。😊，So now you need to check even more， okay。But that's a later lecture。

 so patience on my part。Okay， so a pipeline operation basically what happens in this case。

 so subjecttract for example subjecttract when it gets to this stage。

 there is some combinational hardware dependence check logic that and we will actually briefly describe that logic later on that checks whether register 10 is being written to by any instruction over here over here over here。

 so how do you how can you check that basically you get the destination register IDs of instructions here here here。

😊，And compare。The to the source register，10。Okay this's an equality checker。

 we built this in combinational logic right you have an equality checker。

 you have one equality checker that compares this to the destination register that's coming from here。

 so there needs to be some arc from here to here that gives the destination register ID here here so three equality checkers not only that you should also say you should also check whether the instruction that is writing to that register actually writing to that register meaning there's a right signal to the destination register you should also do the check for the other source so there needs to be three more equality checkers so there are a lot of equality checkers as you can see to check whether there is another instruction。

 the pipeline that's writing to the source that I'm reading at this point， and if yes。

 then you stole this because the value in the register file is not correct for you。

 you just need to wait for another instruction to finish。😊，Okay， so that's detection。😡。

Once you detect， you can stop， but what else can you do？😡，Basically。

 the observation is that dependence between two instructions is detected before the communicated data value becomes available。

 you can do this。😡，You can say， okay， there's a load instruction ahead of me that's currently calculating its address。

 and I'm dependent on it because I know the destination register of both instructions。😡。

But I don't know the data value yet because load instructions did not access memory yet。

 it did not even generate address yet， it's in the execute stage。😡。

So one option is to store the instruction right away， depending instruction right away。😡。

The other option is to stall the dependent instruction only when it's really necessary。

 meaning you know whether the data value is available or not。😡，Because the store， for example。

 the load instruction may actually have already accessed memory。

 but not have written to the register file yet， you can supply that data value early to the instruction that really needs it。

😡，This is called data forwarding and bypassing， and this's going to complicate the pipeline even more。

 but it's going to increase our performance also。😡，There could be other options。

 as we will see later on too。Hopefully that makes sense。

 we're going to cover data forwarding bypassing a lot today。Okay。

 so basically the problem we're going to solve is a consumer or dependent instruction has to wait in the decode stage until the producer instruction writes its well in the register file。

 that's the most conservative assumption we've had， right？😡，嗯。So basically。

 we want we don't want to do this。 Our goal is to not stall the pipeline unnecessarily。

 We want to keep the pipeline moving full and correct。😡。

The observation is that the data value needed by the consumer instruction can be supplied directly from a later stage in the pipeline instead of only from the register file。

😡，If it's available， if and when it's available。Okay， so a later instruction produce its value。

Provide a bus or wire。That supplies that data value to the instruction that needs it。

And we know whether or not an instruction needs it because we built the data dependence checking logic earlier。

 data dependence detection logic。😡，We know exactly what we're dependent on， right？😡。

So we can get that data value also when that data value becomes available。😡，Does that make sense？Yes。

 it makes sense to add a few registers to attach。Yeah。

I mean that's you're trying to optimize it maybe it's possible。

 yes depends on the pipeline design potentially you could actually have some internal registers to communicate these values。

 yes， potentially。😊，But let's not go there yet。Okay。

 so the idea here is to add additional dependence check logic and data forwarding paths and buses or buses to supply the producer's value to the consumer right after the value is available。

So we're not going to add a memory， but we're going to really directly supply with wires。

 if it's a 32 bit value， we're going to supply with 32 32 wires that value to the consumer yes to the consumer right after the value is available。

😡，And the benefit is that consumer now can move in the pipeline until the value can be supplied。

 so there's less stalling。 you don't have to wait until the value is written to the register file。

 Okay so this is this is a problem in a five stage pipeline。

 This becomes a much bigger problem if your pipeline is 20 stages。

You don't want to wait in the decode stage when the value is actually available。😡。

But it's not written yet to the register file because you write to the register file at the end of the pipeline。

 right？😡，So all of these ideas become much more powerful as your pipeline becomes deeper and deeper。

😡，And there's a reason why pipelines become deeper to increase clock frequency， right？Okay。

So now we're going to go into a bit more detail to implement these data dependence handling concepts。

😡，So how do we implement Sting， So this is our pipeline that we constructed Back to today。

 we actually spent a lot of time constructing it。Stall， how do we stall essentially to stall。

 we disable， let's say we want to stall the fetch stage over here。We disable latching the PC。

We disable writing to this writing into the PC， we dis writing into this register。

And if you actually disable those。The instruction over here stays right the fetch stage doesn't move because you don't change the PC and you don't change the instruction over here or actually the instruction over here also doesn't move because we don't change we don't write over here。

😡，So that way you stall these two stages， you ensure that the stall instruction and the deco stage stays here。

Then the question is， of course， what goes here， right？

You detected that instruction is dependent on some later instruction。

 you stall here because you don't change this register。

 you stall here because you don't change the PC so these two stages are stalling right now。😡。

What goes into this register in the next cycle， well， a bubble？😡。

Insert an in instruction or no operation into the stage following the stall one。

 this is the one that's stalling because it's waiting for the data value to be available in the register file。

 assume that we don't do forwarding right now。😡，You need to insert a bubble so how do you insert a bubble Well there are multiple ways of doing that。

 but you can basically invalidate or zero out the entire register so that control signals are all zeros it's like a no no operation basically。

😡，Okay， so let's take a look at this data dependence example and then we're going to build more of this stalling logic so in this example one instruction writes to register a register as zero and next instructions is read this register so all of them read a0 s0 s0 as you can see and this is the destination as0 in the first。

😊，So this is a read after write dependence， we're going to assume the trick that I mentioned earlier。

 a can write into S on the first half of cycle5， so we have this optimized register file where you can write into a destination register in the first half and someone else can read in the second half okay。

😊，So you can see that these are the dependencies。And the instruction reads as on cycle 3。

 obtaining the wrong value。 Clearly we did something wrong。 We didn't stall the end。

Or reads as0 and cycle 4， again obtain the wrong value， only subtract will get the correct value。

So basically subsequent instructions read the correct value of S or from the register file including the subject so basically wrong results happen only if the pipeline handles data dependence is incorrect that's why I don't like calling this a hazard right you need to make sure this doesn't happen。

😊，So okay， this was one option， right？One option is to say， okay。

 I'm not going to add dependence checking logic， I'm going to pun to the compiler and tell the compiler this is how my pipeline looks like。

😡，Schedule instructions such that this doesn't happen。

This meaning instructions getting incorrect results doesn't happen。😡，This is one way of doing it。

 right， the same set of instructions。Add over here。

 riding its resultant destination register in the first2 of the fifth clock cycle。

Compiller was smart enough to insert two noops。😡，To make sure that。

The end instructions that's dependent。Actually gets the correct value。

Basically you need to stall for two cycles you need to so one AM is actually stalling and for two cycles in hardware。

 we're going to see that the other way is actually compiler detecting this and saying， okay。

 I'm going to actually insert two bubbles after this act。😡。

So I essentially insert enough independent instructions for the required result to be ready by the time it's needed by a dependent one。

😊，This requires a smarter compiler that understands。😡，The data dependencies clearly。

 but also the structure of the pipeline。And how data can get communicated through the register file。

So ideal you don't insert No ops， of course， right inserting a no op means you're adding an instruction that is useless。

 right？😡，Ideally， what does the compiler do reorders instructions such that independent instructions。

😡，Come after each other。And if you're able to do that， you can actually improve performance， right？😡。

And there are techniques to do that we're going to talk about some of those when we cover very long instruction word architectures a few lectures later。

but if the compiler cannot find any independent instructions to move or reorder。

 then it inserts no ops in the end。😡，But this is a powerful technique as you can see and this is purely software。

 the only thing that needs to happen is software， meaning the compiler needs to know the structure of the pipeline。

😡，Which is a little bit more than what we have assumed so far from compilers。

 but if you have a smart compiler， it could know。😡，You need to communicate of course okay。

 so let's talk about data forwarding so that was essentially detecting and eliminating the dependence so that you don't encounter it in hardware right？

😊，Okay， so data forwarding is also called data bypassing and the idea again is to forward the result value to the dependent instruction as soon as the value is available。

😡，And actually， we've already seen the basic idea before， not in the same context。

 remember we talked about data flow execution。😡，In dataflow。

 the principle is that data value supply to the dependent instruction as soon as it's available。😡。

And instruction executes when all its data plans are available。So essentially。

 data forwarding brings a pipeline closer to data flow execution principles。😡。

You really supply the data value when it's ready to a dependent instruction。

We're going to see more and this more and more， we're going to actually bring the pipeline more and more into the data flow principles as we cover out ofboard the execution also。

 so it's going to be very fascinating， I think。Okay， so data forwarding。

 let's take a look at the locations of the data path。

 so these are this was the same example that I showed you at as writing to a。😡，Register as zero。

 we're assuming that right happens into the register file in the first half of the fifth clock cycle。

😊，And is reading from that。And needs to read from that。Here。

 like and is really beginning its execution。😡，Really here， right， so actually end。

Operation needs that value。At the beginning of clock cycle4， now let's ask the question。😡。

Is the value？S0 is the value that is named by a0， basically what is produced by this ad instruction available at the beginning of clock cycle 4。

And the answer is。Yes， yes， yes， okay， yes， then the answer is yes。😊。

So let's take a look at what happened to add， a got fetched， decoded， executed， meaning it produced。

😡，The value at the end of clock cycle 3， actually。 And it latched the value。To this register。

 to this pipeline register。Now if you detect it， end it depend on a zero。😊。

You could take that value and put it。As one of the inputs， the right correct input， of course。

Of the ALU and discard what you fetched from the register file。

So and went through the pipeline while ad was executing， it fetched from the register file S0。

 the wrong value， the old value of S0， which is not updated yet。😡。

But we also realize because we design the pipeline that a actually produces its value。😡，Here。

 and we can supply that directly to the input of the ALU。At the beginning of the fourth clock cycle。

 so if we can provide that value directly over here and add a multiplexer。😡。

And that multiplexer chooses between the value coming from the value that we read from the register file or the value coming from this。

😡，Other register， as we will see later on， which is the pipeline register that's at the end of the ALU。

Then we can choose the value that's coming from the pipeline registeror at the end of ALU to get what was produced by a。

Makes sense right so if we add another path another mus another control， yes。😡，有笔的。したか。

Can me kind a shortcut， any instructions。第款。Wch through a usage。

I think it might do a good thing to say。Yeah， you can do it， but that's a different concept， right？

Yeah， this is just to supply the value that's produced to the consumer， but yeah。

 if a value is not needed later on， there could be ways of detecting it。

 but that's a very different concept。Yes。We are going to see it too。Yes。

 you're going to see you suit yes so this is just conceptual conceptual view of the thing so essentially we can supply this from the last output of ALU to sorry last output of the ALU to the input of the ALU so we're going to see this implementation but essentially yes you do connect you need that thing。

😊，Also， let's， let's take a look at another example over here， which is this or。

 this or needs that value and it's actually in the execution stage。😡。

And we know that ad already produced this value。 It's actually added is right now in the register file stage。

 it has not written to the register file yet。😡，But it can supply the value directly from this pipeline register right back to the input of the ALU so that this or can actually execute with the correct value right so this is another forwarding path there is one forwarding path from the output register of the ALU stage to the input of the ALU another forwarding path from the output register of the memory stage to the input of the ALU and then there's an internal forwarding path that we kind of assumed by a smart register file design。

😊，Whenever you write over here to the register file in the first half of the cycle。

 another instruction that needs the value can get it in the second half of the cycle， right？😊。

But that you could have added that Mux is also multiplexs to accomplish that as well。

 so these are the three forwarding paths in our pipeline simple pipeline now let's take a look at how we implemented。

😡，Essentially， this is implementation。What I just said realized using wires and multiplexes。😡。

So this is ALU， remember that ad it produces result， it's routed into this register。

 which is the pipeline register at the end of ALU， we take it。

We add a wire that goes into either of the inputs of the ALU because a dependent instruction may need it as the top input or the bottom input。

 right？😡，And then we need some logic to select between them， of course， right？

So basically from the last output of the L to the input of the L， that's this example。

Meaning you're forwarding the value produced by the instruction。😡。

That's here to the instruction that's just starting executing， okay？Two instructions back to back。

And then there's another forwarding path from here。To here also。

 we are widening that maxs now multiplexer， because the value can also come from an instruction that has moved over here。

😡，And also has done the computation， but has not written back to the register file yet。

 but we want to capture that value with another path。😡，So we send that value， widen the small topor。

 change the control logic such that we actually decide which one， which value to take。😡。

And then we also get that from the register file， which we assume there's some internal forwarding。

 which makes this picture easier， let's say assumption of that internal forwarding makes this picture easier or a smarter register file。

 half of the clock cycle， you' write， half of the clock cycle you read。😊，Okay。

 so now you can see that this is not that bad， but it' increased our complexity and you can also specify the logic。

😊，Of which。How to control how to control this mark。Essentially。

 if the instruction here is reading a register。That's written by an instruction that's over here。

 you should get the data value from here。😡，Otherwise， if it's reading。😡。

A value that's written by an instruction that produces the value over here。

 you should get the data value over here， otherwise you should get it from the register file， right。

Why， because you should get the latest。Definition of that value。

 your latest version of the register that's written。 This is the oldest instruction。

 This is the youngest instruction that writes to that register that you may need。找的是。Older， younger。

 youngest， if you will， right？Okay， so this is essentially the design of the forwarding。😊。

We basically now forward to execute stage from either memory stage or right back stage。😡。

And then I think I kind of answered this question earlier。

 when should we forward from either memory or write back stage if that stage will write to a destination register and the destination register matches the source register that we're sourcing from if both the memory and write backt contain matching destination registers。

 which is possible， it's valid， it's allowed memory stage has priority to forward its data because it contains the more recently executed instruction。

Basically， it says that you give priority to this red arrow clearly because it is the younger instruction that's producing the value。

Okay。😊，Okay， so if you want to specify this using some logic， your book does it。

 I will not go through it， but essentially you can specify it， you can write the very log。

 there's no magic after this， as long as you can describe the logic you're doing in a logical way。

 you can put it down as in very log right。😊，But you can read this in your book。

 it's basically in pseudo code， you can write it very very easily。Okay。

 but you need to do it for both source registers， source register A， source Reg B， right。

 there are two source registers potentially of a given instruction。😡，Okay， so that said。

 forwarding is not always possible， depending on the structure of the pipeline and the lates of instructions。

 you may not be able to forward data in our pipeline， there is one case where we cannot forward data。

😡，When you have a dependent instruction that follows a load instruction immediately。

Forwarding is usually sufficient to resolve theses。

 but there are cases when it's not possible due to pipeline design instruction latencies。

 for example， the load instruction is producing a0。😡，When does the value become available。

 it becomes available after the load instruction actually accesses memory and gets the data value rate。

😡，When does end instruction actually get to the execute stage in the same cycle？So basically。

 at the end of cycle 4， S becomes available， but end instruction moves to the execute stage。😡。

At the beginning of cycle four， so it really needs to be data value at the beginning of cycle four。

 right？😡，Essentially。Its result cannot be forwarded to the execute stage of the next instruction。

Right well， it can be。But we break the critical path current with principle。

Meaning what we can do is exactly what this trouble arc says， we take the value。😡，From here。Forward。

 it's here。And now we have a very long， critical path。Right as opposed to having one memory access。

 latching the results， we have one memory access， get the data supply to the ALU。

 do the ALU operation and then latch the data right so you don't want to do this forwarding because it doubles your critical path probably something like that essentially it breaks our critical path design principle essentially。

So what happens is you need to stall the end in this case。

 this is the only condition where you need a stall unless you have like a long long laency operation。

 which we're ignoring for now。😡，Okay， so essentially stalling is necessary for this memory to execute dependence。

😡，So these instructions need to stall when that dependence is detected。

So let's take a look at that stalling independence hardware detection hardware。

 this is again from your book， you can see it more in your book。

 there's some dependence detection logic。😊，呃。So how do you actually stall that's what I would like to point out over here your book has the complete picture but essentially stall means the instruction the decode stage should not move to the execute stage y because this end instructions in the decode stage over here it should stay in the decode stages you can see over here right it stays in the decode stage for two cycles until the value of the load word is available and it can be forwarded here this is the nice forwarding path clean forwarding path you get it directly from the last output into the beginning or input of the AL we already added that forwarding path this also needs to stall of course right okay so in order to stall you need to make sure later stages get inserted no ops so your book does it by clearing。

😊，The pipeline register。In the stage where the instruction is stalling。

 this instruction is stalling over here it cannot move。

 there should be something that moves into the pipeline register and it's a no essentially so you clear the pipeline register such that no harm is done。

 it's a bubble。😡，And then you actually have these enable bits。hich I already discussed actually。

 that dis latching for this register， I that this instruction doesn't move and for this register。

 which is the PC so that this instruction doesn't move。😊，Okay。

 so we've already seen this that put it in words， stores are supported by adding enable inputs to the fetch and Decode pipeline registers and clear inputs to the execute pipeline register in the simple pipeline or you can have an inved bit associated with each pipeline register indicating that contents are invalidved or valid and taking action based on that validity that there are multiple ways of implementing this that I will not go into detail over here but。

😡，The concept is simple， you need to insert a bubble basically。If you're stalling。You cannot move。

 but something else needs to move to the next pipeline stage， and that's aO op。

 Okay this is very similar to a compiler inserting your bubble， which is a no op instruction。

 but the hardware is inserting it right now。😡，Okay， so when a load word stall occurs。

 you keep the values on the equal and fetch stage pipeline registers， Sta D and St F are asserted。

 and you clear the contents of the execute state register introducing a bubble。😡，Okay。

 flash is also I started， but I'm not going to go into that so your book actually does a good job covering this if you are interested in learning more。

😊，But I've covered essentially everything you need to know。Okay。

 let's talk about control dependence right now because this is going to actually occupy a lot of our time for some lectures after Out of order execution。

😡，Data dependencies we've handled hopefully right memory， I think you know how to handle right now。

 if memory takes multiple cycles， you do the same thing， stall everything that comes before。😡。

Inject bubbles to everything that comes after right anytime the pipeline cannot move。

 you know how tand this right now， there's a general technique。😡，What about control dependence。

 there's an elephant in the room over here because control dependence is actually arguably bigger than everything that we have seen。

😡，So what is the control dependence， Control dependence theory is really。

Some dependence on the program counter。It's really data depends on the instruction point or the program card。

Meaning， okay， this is the question and control depends。😡，What should I fetch in the next site？😡。

I fetch this instruction， it mostly decos age， what should I fetch in the next cycle， right？😡，Well。

 you would say the address of the next instruction， right？

And all instructions are dependent on previous ones in an oneknow machine。

 you have sequential execution， you increment the program counter by four right in MIPS。😡。

So that's the reason why all instructions are controlled depending on previous ones。😡，So basically。

 by fetching the next instruction， PC plus4， we're implicitly making an assumption。😡。

The next instruction is the next sequential instruction。Most of the cases， this is true。

Meaning if the fetched instruction is a noncontrolll flow instruction。

 next fetch PC is the address of the next sequential instruction。

 this to determine if we know the size of the fetch instruction。

 and we already do a PC equals PC plus4， and then we fetch the next instruction that way。😊。

But what if the instruction that is fetches a control flow of instruction？😡。

How do we determine the next fetch PC？😡，Okay， that's a good question first。In fact。

 how do we even know whether or not the fashion instructor that control flow instructions。

 we haven't decod it yet。😡，So we have a pipeline， we have the fetch stage， we have the recode stage。

😡，We fetch the control flow instruction， we don't know if it's a control flow instruction。

 most of the de stage， only at the end of the deco stage， we know it's a control flow instruction。😡。

But we're already fetching the next detection。If this is a taken branch。

That me fetch the wrong instruction， right？So that's the problem。

 that's why this is so fundamental because of the sequential control dependence that we have and control flow dependence。

 we need to be very careful。So essentially you can do something called branch prediction which we will see more this is a special stage of data dependence depend on the PC remember BEQ conditional branch is not resolved until the fourth stage of the pipeline when we actually execute in the ALU produce the result last the result and then and then actually change the program counter from the last output of the ALU。

😊，Instructions after the branch are fetched before the branch is result。

So we kind of implicitly speculated， essentially fetch instruction into the pipeline without knowing that we should really have fetch time。

 right？😊，So this is a simple branch prediction example。

 you always predict that the next sequential instruction is fetch。

 it's also called always not taken prediction。😡，If you are wrong。

 you flush the not taken path instructions if the branch is taken， basically it the branch。

 you figure out whether or not the branch is taken when the branch executes and you actually determine the condition。

 if the branch is actually taken， you flush all of the instructions。

 flush means clearing all of those registers。😡，So you know how to actually clear your register is not。

 right？Okay， so basically there is a misrediction penalty。

 number of instructions flushed when branch is incorrectly predicted。😊。

Penalty can be reduced by resolving the branch earlier。

 this is also called early branch resolution Now let's take a look at that element this is our pipeline so far。

A branch instruction look over here， it's actually a conditional branch is resolved over here essentially this is it's really updating the PC over here so branches here。

😊，Asstume that the branch is not taken。 We fetch the next instruction here， next next instruction。

 next next instruction here， everything is good。 Branch is not taken， so we did the right thing。

If the branch was taken， when we execute the branch， it's taken。😡。

We fetch the next instruction over here PC plus4， but we should have fetched from the target。

 so this is wrong clearly this is wrong， clearly this is also wrong because we fetch PC plus 4 PC plus 8。

 PC plus 12， whereas we should have fetched target target plus  four target plus8。

 assuming none of those are branches either。😡，Okay。

 so basically that's the problem we this is branch instruction， it resolves in cycle four。😊。

And we have fetched 24， 282C， as you can see， consecutive instructions。

And when the branch instruction resolves， we need to change the program counter to 64 because you can calculate the target at 40 plus 20 plus 4 PC plus 464。

And that happens in cycle five when the branches result in cycle4 that gets communicated to the PC in cycle five。

 you fetch from the correct T and in the meantime you need to get rid of these instructions that you fetch into the pipeline。

 those are wrong。😊，So， you flush。Meaning you clear those registers right， that's it。

 you just need to clear those registers and you're done。😡。

Because those instructions did not do any harm so far。They did not write to any register。

 they did not write to memory because of the structure of our pipeline。😡，As a result， we can do this。

That sounds beautiful， right？So now you're seeing the example of a simple branch mis prediction。Okay。

 now let's try to make this a little bit better， we want to resolve the branches a little bit earlier。

😡，We can actually do that at the expense of some things。 So branches。

You actually know the register route， so let's look at the branch equal right branch equal the test two registers。

 register one register two， you compare two registers， if they're equal。

 you basically set the program counter to the target program target PC that you calculate。😡。

So basically you can have any quality checker over here that you add after these registers。😊。

And then basically， if it's a branch and if the equality checker says equal。

 then you basically select the program counselor target address。😊。

From the sign extended left shifted immediate， added to PC plus4。😡。

So you do the target address calculation here and you also do the branch condition calculation in the decode stage。

 we move everything to earlier so that we don't flash more instructions than needed。And then you。

 of course， if it's a branch， you need to clear this one， right？That sounds good， right。

 You could do it。Clearly， this will have some benefits if you do that。

 you need to flush only one instruction。😡，You don't need to fetch these instructions basically you fetch the next instruction and the branch resolve at the end of clock cycle2。

 so at the beginning of clock cycle two you're at the target address。

 so you fetch only one useless' instruction， you flash only one of those。😡，The question is。

 is a good idea？Yes。I mean， wouldn't we increase exactly Yeah， so advantage。

 let's start with the advantage， you reduce the branch mis predictionction penalty。

 you reduce the cycles for instruction， which is good。😊，Potentially。

 you increase the clock cycle time， in fact， probably you have increased the clock cycle time。

 meaning you have a higher clock period and lower frequency。

You also have additional hardware cost in addition to increasing the clock cycle time。

You have a specialized hardware that's likely not used by any other instruction。

 who else is going to use this hardware？😡，Let's say no one other than the branch。

We do it to reduce the latency of the branches， but we increase the clock cycle time for every other instructor。

 is that a good idea， well， you need to evaluate essentially。😊，You need to evaluate based on this。

You need to figure out how much did I increase， did I reduce the average CPI。

 how much did I increase the clock cycle time， if the result is net positive。

 maybe that's a good idea assuming the hardware cost is not too much right？😡。

But based on what I know and based on this pipeline is' probably not a good idea in this sort of pipeline in some other pipeline。

 it may be a different thing。😡，Okay， that's not the end of it。We forgot the data forwarding。

 meaning where does the how can we resolve this branch？😡。

This works what I just showed you works actually。😡，Only if the data values。

Of registers are available for the branch to correctly calculate。 But if they're not available。

 but if there are instructions over here that are writing those and there are very likely instructions there because branch is actually dependent on some instructions that produce those registers。

 So you need to forward those registers。 So whenever you add whenever some computation。😊，Earlier。

 you need to actually forward the data also， so there needs to be a forwarding path from here to here as well。

😡，Okay。So it adds even more complexity， it increases your critical path， even more potential。

 This is from your book forwarding logicEssential this is the full store and forwarding logic you can you stole because of an instruction is dependent on a load that has not produced its value yet。

😊，Or you can stall because there is a branch right and that branch， you mispredicted the branch。

And this is your final pipeline mis Pro from your book。

 it includes always not taken branch prediction， early branch resolution， forwarding and stall logic。

 it's complete， it's nice。What it doesn't include is multi cyclee memory or multie operations。😡。

That requires a little bit more work。So it's still not a realistic full pipeline。

 it's assuming magic memory with one cycle access。😊，So okay， doing better， smarter branch prediction。

 This was not so smart， right， we basically said。We're going to implicitly assume that PC will be incremented by four right It's the called always not taken for prediction。

😡，But you can be a bit smarter。 You can guess whether or not the branch will be taken right and existing processor actually are quite smart。

For example， backward branches are usually taken because loops iterate many times if you see a backward branch。

 you basically predict it taken right？😡，You can take keep a history somewhere in the process as we will see in later lectures of whether branch was previously taken and it can improve the guess based on that history if you've seen branch was taken a million times you say okay probably it's going to be taken again。

 you can be even smarter as we will see。😊，So accurate branch prediction requires the fractional branches or reduces the fractional branches that causes a flush。

There are many sophisticated techniques that are employed in modern pro to do accurate branch prediction。

 and the reason hopefully is clear because if you are incorrecting your prediction。

 you fill the pipeline with junk， junk meaning useless instructions， you're going to flush them。😡。

So you'd better fill the pipeline with useful instructions and the only way to do that is。😡。

To predict。The correct instructions to fetch from。So in fact。

 existing machines you use simple machine learning methods to learn as well。

 simple because hardware implementation of complex machine learning methods is too slow for high frequency operation。

😊，And we will see a lot of these N branch prediction lectures。

 it'll be a fascinating overview of what people have done in 60 years of branch prediction。

 let's say。😊，If you're impatient， you can watch the earlier versions。But hopefully not。

 we'll get to it。Okay， I think I cannot I do not have time to cover pipeline performance example。

 I will leave these slides for you to study it's a very simple example it's in your book also and next week we're going to start with some other issues in pipelining and then we're going to build up to automotive execution。

😊，So have a good weekend， I'll see you next week。

![](img/1cd3d778f057152b7fcc509fdddc6cba_2.png)