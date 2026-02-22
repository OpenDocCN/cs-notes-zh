# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p36 -36-  L27_ Problem Solving II (Spring 2025).zh_en -BV1iV1XBWEJW_p36-

microcrophone。Yeah。老。O。你是。cosantina哦。Yes。嗯， hellello。いで。I feel now I have a power。Okay， cool。

And we still have2 minutes。あ。Constantina，2 minutes。哇。Yes， let's go。Hello everyone。

 welcome to problem solving session of DDCA， so in the session we will solve questions from spring 2023。

I get how many questions like 10 or something don't count on that。Okay。

 so I'll start with IA versus my correct picture， it will be a rather quick one。

I'll like to choose the color first， Okay， I'll choose red。So。The question is， circle。

 whether each of the following is an aspect of the ISA or the micro architecture。

So we have 15 questions here and you're going to choose which one is like IA or market architecture。

 for example， let's start with the first one。The width of the immediate value in the add instruction。

 which is defined in ISA， so we select IA here。And the second one the algorithm used by the ALU to perform multiplication。

 so this has nothing to do with IA and this is defined in the micro architectureiture。

 so the correct answer is micro architecture。A number of bits required for indexing the source register of a store instruction。

 so this is definitely in the instructions at architecture where we define these things and so that's why it's ISA and number of entries in the Al cache。

 this is a design choice， nothing to do with again IA so it's microarchitecture and the data cache organization little for that it's the same again microarchitecture。

S1 support coming prefeing hints to the hardware via compiler so this is ISA again not again this is ISA and available data types where atmetic and logic operations and this is ISA one example could be like risk 5 I which is just for integer is 5 ifFM and folding points and so on so this is ISA。

And the cache coence protocol and multiguard processors again designed just this microarchitecture and the width of the data between processor and main memory。

 again， micro architectureitecture， this is not defined in ISA。

And the memory controllers memory request scheduling algorithm， again， mark architecture。

11 question instruction encoding for data control flow and branch instruction。

 again instruction encoding it says so this is defined in ISA and the design of the register renaming logic it is again the design shows that microarchitecturally done so again microarchitecture number of instructions decoded percycl and super scalar processor so this is based on your bit and the microarchitecture so again。

My grand。And2 cache mislatency， this is not defined in ISA。

 so this is basically depend on the protocols that you have， how big your L2 or the other let's say。

 caches you have， so this is again microcraft architecture and the width of the program counter is ISA。

So that was a rather quick one， so yeah。I hope it will be quick for you as well indeeda， thanks。Yes。

 so the next question is the pipelineing question。This one is a relatively long question。

 but it's very easy actually， so let's get started one second。We need a lot of colorful pens。

 it would help you in the exam also if you can use it， I don't know if you can use it。

 maybe you can check that。Okay， so。Okay。Here we have a code listing which contains a piece of assembly code and table one presents the execution timeline of the code。

 so right now we don't need to understand at this point what this code does。

 but it's described in this comment site if you're struggling with the instructions。

So everything is basically explained in this part like line by line。

 and next we have this exhibitionion timeline which shows the pipeline stages that these instructions are in in each clock cycle。

 for example， in the first one we see that the first instruction is fetched。

And then it goes through the pipeline and so on， so the question says use this information to reverse the engineer the architecture of this microprocessor to answer the following questions and answer the questions as precise as possible if the provide information is not sufficient to answer question you can answer unknown and explain your reason clearly。

And the first question， the first part of this question is it asks you to list the data forwarding paths between pipeline stages。

 so the data forwarding paths basically they enable you to use register values that are not yet written back to the register file so you can basically forward the of result of an instruction early to the next instruction if the data forwarding path is implemented in the micro architecture so for this part we first need to identify which register values are used before they are written back and to do so we first need to understand the data dependencies so I will just mark some of the registers that are used throughout this instructions so here we first have R1 that is written so here you can see that the value stored in the address access stored in register one so this is our first register。

And then I will use different colors for different registers。

 so here we have also r2 and here on the third instruction you can see that r1s value is used to calculate r4s value so you do a multiplication you multiply r1 by R1 and then get r4 so you can see that the register's value is used this way and the next one we again have some R1 here as the input and as the up and also we have R2。

And you can also see that okay we need more colors。

 you can also see that now we will write back to R1。

 the result of this instruction this multiplication will be written back to R1 which changes its value so I will just market with another color and next we have an instruction with R4。

 R5 and R6 these are not related to the earlier ones。

 you can also think that okay R4 was written here is that does that create a data dependency。

 the answer is no because you basically overwrite the result in the instruction5 so it's not red。

 it's written again。Okay， so let's get the sixth one。 Again， we have our two as the opera end。

 so that's be。Mark， and now， okay， I ran out of colors。我迪是。Maybe I can use this。Okay。

 so now we have our four。This is slightly a different color。

 but you cannot tell probably it's okay and the value was written in the instruction five and then we use it here and after that we again have。

R 1。Wch is here。Thank you， I think this is， it's fine， but let me let me mark it differently。😊，Okay。

 so and then this is like the last instruction that we will talk about registered dependencies。Okay。

 and based on these now we will check the pipeline stages and see how these are read before if they're like read before the right back stage so let's start with first one as you can see the first dependency that we will talk about is here which is reading r one's value and this instruction was fetched in cycle3 and then they call that cycle4 and then we wait for the result of the first instruction here to be ready and after that you can see that we immediately go to execution stage without waiting for the right back to happen in in the cycle7 so this means that once the value of R1 was ready。

 we forwarded to the first execution stage for this instruction to continue execution。

So this shows us a data forwarding path from E3。To E1。 And this was coming from。嗯m。R1。Value。

Is forward。You can also say that in which cycle like cycle six shows this。

So that would be make it easy for us to understand your reasoning so that's good and after that let's check the next instruction here I'll show you with this with again R one we see that after this instruction was decod it moved on to execute in immediately I will show you with a different1。

You can miss this one actually this is a bit more tricky because basically we saw this like data forwarding path from e through to E1 for R1 this time the same value is forward to E1 from the this stageM stage memory。

Again， we are not waiting for right back to happen。So this feel right。 Oh sorry， M to。E1。

 again for R1 value。Okay， and next you will again continue with the instructions here。

You can also consider R2， but this is the same forwarding path as the instruction to。

 the result of the result that will be written to R2 is in E3 and then it is forward to E1。

That's the same forwarded stage as we showed earlier， so I'll just。

So it's like an example of this again。Okay， so let's continue here。

In this part we already evaluated this so in this part we don't have a data dependency so I'll just skip it and in next one what we see is we have a dependency for R4 and when this so this instruction was fetched that cycle7 we code it next and then made for a couple of cycles and after a while it is executed in this stage and。

The value of R4 was available here， so again you can see that this is the same data forwarding path。

Okay， so。嗯。Next， we have this。Instruction7 and here are one you don't need to really consider a data forwardbiing path for this one because when this is executed or decoded our one's value was already written back in this stage so it's like an early stage already so you don't need to consider any data forwardbiing path for this one so another one that is sort of hidden in this part is that when we consider the instructions you can see that in this instruction eight。

We do an execution we calculate R3 based on R1's value， but basically subtracting 2K48 from。

The R1s value， and then after that we have a jump instruction here。And this jump instruction。

 what it does is basically it jumps to the label L1 if zero flag is not set。

And you can see that the previous one， previous instructions has this condition flag。

 so it depends on that basically it depends on the result that is written to Earth or basically the result of this。

Computation， so。To be able to execute that that dependency needs to be solve and here we see that this instruction is fetch at this cycle 11 and then de quoteded and then wait for a couple of cycles and execute that this part。

 so you can see that after the execution is done， sorry。

You don't need to really do this because that's not the part of the execution。

 So basically at this point the result is forward to the。Condition registers or yes。

 and then there's one data forwarding path to from E3 to condition。Registerters。And after this point。

 we don't know anything else because these are the instructions that we see and this is the pipeline that or like the timeline that we see and。

If there are other data forwarding paths， you cannot understand from this timeline。

 so this is the correct and completete assay。Is there any questions， yes？Okay。是。FF。Os。So。嗯知道。嗯哼。😊。

根据告。在对。是他。So in this particular question， I guess we assume that the data forwarding path is from the previous cycle to the next one。

 but it should be clear from the question that what we should assume。

 basically maybe you saw a different version of the same question。

 which has a different code but then it has another assumption you can write that okay。

 this is my understanding of the question if it's not written there like this is what we assume。

And then we will evaluate it the same， so it doesn't really matter basically unless you show wrong data dependencies。

 if the data dependencies are correct， this should be correct。ok。Are there any more questions？Okay。

 now then let's move on， let me find the rest of the question。Okay。Yeah。

So in the next part that I will show like this in B。

 the question ask does this machine use hardware interlocking or software interlocking and explain why so when we look at the timeline here。

 we don't see any bubbles or knobs inside this like instruction sequence right this shows us that the machine itself the micro architectureure detects data dependencies and then stalls the pipeline stages which is in hardware which is done with hardware interlocking。

 so the answer is hardware interlocking。And we would expect you to write the same explanation。

 but I will not write it in the interest of time。Okay， so next。

In this part we are doing a little bit more like reverse engineering again。

 so for the rest of this question assume the following X 4 y is2 in the code listing1 and branch predictor always predicts correctly。

 the mission uses hardware interlockin and now this part of the question will give you a state based on this so at the given calledg cycle T。

 the value stored in R1 is 1024 and the processor fetches the dynamic instruction n which is multiply r for R1 R1。

And。I'll just show you the code and the timeline as well for this。😔，Okay， maybe I'll just。Yes。Okay。

So calculate the value of T the clock cycle of the given snapshot and show your work。

 so here what we know is that。At this snapshot， clock cycle T。

 the dynamic instruction that we are fetching is multiply， which is multiply R4。

 which is this weight， this instruction。And then what we know is basically we started executing with x equals 4 and y equals 2。

And now basically get this value we need to first。Look at like the general timeline a bit more one second so。

Okay。So let's get what this code does at this point。

It starts with moving the values of x and y to r1 and r2 at this part you can see it right r1 becomes4 r2 becomes2 and inside the loop so this is like a loop。

As you can see there is the jump to the start of the loop， the first instruction does the following。

 so it writes to R4 by multiplying R1 and R1， which is4 multiplied by 4 and 16。

I that correct yes and then in the second part it updates r1 by multiplying R1 with R2。

 which is4 multiplied by 2 which is8 and then we have an addition but this is not relevant to the code because it uses basically a hint of your is a hint for you is basically it uses some unused and undefined register so you can maybe not think about it in this part it's not important for the loop and then next we have another instruction basically changing the value of r5 which is again not relevant to the question and after that here we have a calculation for r3 and what it does is basically it does this calculation and checks and next it checks if r3 is zero。

And then either continues or jumps to the start of the。

Loop so here you can think of this as like a condition it checks if r1 is if it reached to 2048 right so this is like a simple code that basically multiplies r1 with r2 repeatedly inside the code until it reaches 2048。

And basically what we expect is that with these starting values。

 it should execute the whole loop a couple of times and then reach this clock cycle T。

And what we know is that at that time our ones values this 1024。

 which then we can calculate how many times this loop has iterated right， so we start with our one。

For in the initial part。And then inside the loop。We have R1 value that is equal to8 at point at this point。

 the first iteration， and in this second iteration it should be 16。

And then it goes on our of1 equals to 124。Okay， I guess at this point you can understand how many times you need iterate this。

 but let me tell you it's。😊，Basically，我。😔，One second。Maybe you can also say that。

I see someone whisper， basically it should execute like eight times。你。And based on this。

 now we can calculate what T is。And now we have to look at the。

The timeline to check how many times you need to execute this loop。And。Let me do it one second。

So okay， let's look at the first iteration of the blue， which is here。

 you can see that after this point since the branch prediction always brings the correct instruction。

 what you will get is another multiply r4， R1， r1， and this makes this part from instruction 3 to8。

 basically one， the first iteration right？So you can now see times how many cycles you need to execute this by completing this part。

 maybe。And then， it's 17。点。90。Okay， then when you complete this。To get the next instruction。

What you have is this instruction will be fetch at cycle 12 and then decoded and since it will use the R1 value。

 you need to check。The data dependencies again， so the last time the R1 was executed。

 was written back here。And then we don't have in data dependencies next we will look at the stages since the execution one stage is busy with oh okay。

 this part is wrong， so we cannot move on to decode because this instruction stays at thecode at these points right and then when it's ready we will get the decode stage and then execute and go on。

So you can see that the first loop。That was fetched at this point and basically the next fetches here。

 it takes like nine cycles。Until the next pitch。And。

Thats here is a little trick basically that's different than the next iterations because we will have basically an extra one cycle here that is coming from this stall because this is different than the first fetch that is here so maybe this part was a bit confusing do you want me to explain it again？

😊，Okay so we first looked at the first iteration and then calculated how many cycles it takes and then we've checked the next iteration by starting the instruction that is basically our snapshot instruction to understand if something changes in the second iteration and at this point is what we see is the execution of the first iteration of this instruction and the next one differs because we have one more stall in the deco the pipeline stage so this is why the next iteration will have one extra cycle compared to the first iteration is that clear。

😊，I see some notes。Okay， so this means that okay， first we have two cycles coming from initialization。

Two cycles。 And then the next。The next loop iteration， which is the first loop iteration。

 will take nine cycles。And then。Okay， I do something wrong， okay， so this is three actually。

Because we are calculating like this and then。The next iterations。

 which are like seven iterations because we counted the first iteration here will take 10 cycles and after this point you get。

The slump。Okay。Now okay， then let's move on to the next part。Yes。Next。

 the question asks the calculated value of n N was the number of basically the。Let me show you here。

So n is defined like this， this is like the account of the dynamic instructions at this point that where we fetch this instruction。

So basically what we are looking for is， okay， I'm showing you the result actually。Yeah。Yes。Okay。

 so what we're looking for is basically here we have our instructions。

So this is like the first fetch of the instruction that we're interested in and this is the second fetch and after a while we will have like the third and so on like for eight iterations we will have in total nine fetches of this instruction or eight it's not important basically。

We will try to get this like the count basically here and。Okay， so we are interested in this number。

You can calculate this based on the number of iterations that we have， which is eight。

 the first instruction is the dynamic the first iteration of this instruction is the dynamic instruction3。

 and then the next one is nine。Because we have six instructions in between those。

 this is like the loop invariant if you or basically the number of instructions that you have inside the loop。

And we will continue。Like this， so we will add like sixes and sixes and so on。

 and basically what this guest us is at the end of eight iterations。We basically will have， sorry。

I'm checking if I missed something， so since we have eight iterations of this。

 we multiplied by six the number of instructions inside the loop and we will have 51 as the n value so n is 51。

Was that clear？Yes。Basically I。I use this timeline to basically we have the initialization phase and then it's like the third instruction that we have and then after a while we will just fetch it。

Eight times。Until the last one。Is that clear？我来。See。そう。

2 plus eight times six and then so after eight iterations we are pitching the new one that is starting the next iteration like it's like actually the first first instruction of the ninth iteration so you get the plus one。

Based on that。Okay。Okay。So in this part。Now。Okay。Now we are looking at this the question asks like lastly like calculate the total execution time of the assembly code in code listing one and until the completion in terms of number of clock cycles and it asks us to show our work so for that we need to figure out when this code ends and when we look at the code itself we see that it basically this jump always goes to the label1 unless the R1 value is is equal to 2048 right so the last update of the R1 value should be making it 2048 so let's again write like what changes in terms of like iterations in the first it after we execute the first iteration we get the R1 value。

8ight and then it it is multiplied by two and then it is again multiplied by two and then we go on till the end and at the end the last update should make it 2048 right so you can see that this is like。

And then this is this and we basically see that。Yes。

We basically see that we need to iterate like nine times to get to this point， right？Okay。

 and let's look at the timeline to get the total execution time again。 So here what I will do is。

Following， this is getting a bit crowded， but let's see if I can make it clear。す。Okay。Yeah。

Here until the end of the first iteration， basically this is the last right back written the first iteration right。

 this is like last instruction and then it's written back at this clock cycle。嗯。We can also use the。

There are two ways to this and I' am confused about which won't follow so let's use this calculation so here what we did is we calculate the time it takes for us to get until the second iteration of the loop so with also including the initialization it takes12 cycles and after that point we need to execute the loop seven times is it seven times。

😊，Yeah。I'm sorry， this is getting a bit weird。😔，嗯。Yeah， so we need to calculate we need to do the。

Loop seven times， so plus 12 plus seven times 10 will give us the execution time。Oh， I messed up。

 I'm sorry。One second。は。Yeah， okay。Let's let's move on， let's basically use the second version。

 so okay， this is like the end of the first iteration。

Of the loop and it takes us 19 cycles and then after that since we use the we include the first iteration here。

 we have eight more iterations to go for and then it takes 10 cycles as we calculate it in the previous parts and then after that we need to also execute one extra instruction and then that will like execute at the end of the execution of the whole code and then we will have 100 sorry about mass。

 do you want me to recap。That was blind， okay？Alright。Yes。はい。So。还是。Please。So。Make a reason。Yeah。

I think there's more it's all under。Okay is true。什么事有。Okay。有房子。对。不错。Right。She。Yep。晓的。Right。Okay。

 so I will deal with three questions， we will go in a different order than the paper。

 we will go with memory poetryri first。Then we'll discuss finite state machines and better processing。

Let's do memory property first because the previous question was a bit difficult。

 let's start with something simple。So the question is as follows。

Read the following statements about memory organization and technology。

 so could true if the statement is true then false our device。And yeah。

 you lose two points if you have an incorrect answer。So you want to be sure here。The first one。

 a main memory access typically has larger latency than a register file axis， this is true。

Particularly because of the long pit liness and the distance from the core。

StraM is commonly used as mean memory in modern computers。

 this is definitely not true use DDM as mean memory。嗯。

DM cell requires larger part to store data compared to an STM cell， so this is two components to it。

 the static part and the dynamic part。The asstr cell requires a higher static part because of the larger number of transistors used to build an asstrM cell and this generally。

Outrights the dynamic part。This is incorrect。Right。

 reads are faster than write in Dam this is not true generally both of them have similar。Rates。

 so this was faults。Reads are faster than writes in face change memory。

This is true because in phase change memory。You read data by measuring resistance， but to write data。

 you need to change phases which takes longer。So this is true。

A bit line in a D array array connects all D cells。In a Dm row to the row decoder circuitry。

This is incorrect。 So the row decoder is usually something like this on the left hand side。

 it's used to open up a row。And you have bit liness running vertically。

So the bit line is really connecting all rows across。

Essentially all rows in the DM Bank and they're connecting it to the sense amplifier so thats false。

Next one using virtual memory reduces the memory access latency using virtual this is not the motive of using virtual memory in the first place and some would say that you would increase memory access latency when you use virtual memory so。

It's false。Face change memory is non volatileat and this is true， you don't lose data。

 you don't need to refresh。嗯。Next one， if a hypothetical service system is not constrained by chip area。

 memory cost and energy consumption， PCM would be the best memory technology to use in that system。

The problem with PCM is right endurance after some number of rights。Your system。

 your memory is no longer reliable。So by that metric。Well。

 you can't quantify and say that PCCM is the best memory technology in that scenario。

 so this is false。If you were programme， so a program with a streaming memory access pattern。

 this would lead to very high memory locality in the last data level cache。

A streaming memory access pattern basically means you access a different element。

Across different cycles， different times timess。This is not temporal locality。

 temporal localities you access the same element。Across different things stems。So this is fault。

Indeed accesses to different rows in one bank can be serviced faster compared to accesses to different rows in different banks。

This is false if you have requests going to a single bank， so look at this picture here。

 if you have to access data in different rows， you need to close a particular row and then open another row。

And this is longer than， let's say， having another bank。Where you access a different rule。

Because you can have these rows open parallelly using bank parallelism。So this is fault。

A TLB is a specialized instruction cache， this right away is incorrect。

 it's a translation locoocyte buffer， you cache translation entries here， not instructions。

Virtual memory simplifies software design， this is 100% true because you no longer have to deal with physical adacies。

 you see an infinite memory space。And you don't need to worry about what these values are。

 the infrastructure， the computing system handles this all behind the scenes。

A page4 happens when the TLV does not contain the entry needed by an instruction， this is false。

 it happens when you don't have the translation entry essentially when you don't have the entry that converts the virtual address to the physical address。

 so this is also false。A fully associative L1 KLB that only stores 4 kilobyte virtual to physical mappings。

And has 1024 entries can cover up up to four mebyte memory。

 This is true you basically just multiply these numbers because you have V2 P mapping size and the number of entries and therefore you can cover up 4 kilobyte4 kilobyte times。

1024 number of let's say， physical addresseses。呃。For this physical addresses season this basically evaluates to four megabyte and that's true。

Any questions up to this point？K looks like this was very clear。Good， let's then do。

A slightly more difficult one compared to the memory appropriate， at least。Finance state machines。

So we have two questions here， first one is to simplify an FSM and the second one is to design an FSM。

Um。On simplifying an FSM， I hope this is is this visible enough or cool。

So you're given the final state machine of one input one output digital digital circuit design。And。

Yeah， you need to answer some questions based on this state diagram the first one is can you simplify this particular state diagram and reduce the number of states so currently we have four states ABCD。

And if you can simplify to the minimum states and you should explain。

Every step of your simplification， you draw the simplified state diagram and if you cannot。

 you should explain why。Right off the bat， one thing that you can notice here with each of these statess。

 A， B and D。They have very similar input output patterns。For example。Let's start with a。

And by the way， the noclature here is the left hand side of the slash is the input and the right hand side is the output。

 as suppose this is very clear from the lectures。For a， when you see zero， you output the one。

When you see a one your output is zero， essentially inverting the input as the the output is basically the invert of the input。

This is the same for B， when you see one then you go to zero， when you see a0。

 you go to1 and the same also is true for B。This is also true for C。So essentially。

 you can come down to a single state。And perform this logic essentially what you really want at the end i'm not going to go step by step here I can go the solution describes it step by step okay let's actually let's go step by step so let's say the current state。

I will describe it。In the format that it's described in the solution so that you can follow if you couldn't follow it from the state diagram。

So let's say we have the state transition table as。Phools， so let's have。The states for a。

 let's say you have an input 0。 The next state is a。The output is going to be one。

Let's say you have the input one， the next data is going to be B。And your output is going to be zero。

If you were to do this for all the states。You notice exactly what I was describing。

 let me quickly populate this。So B on zero。Gose。Beyond on 0。I'm missing something here， Yeah。

 B zero goes to a。Beyond on one， stay B。And the output here is going to be 10。

 let's fill up the output。And。For C。Then you have an input of one， you grow a。

 when you have an input of 0， you go。To地。And for D， when you have an input of0， you go to a。

And when you have input of one， you go to B。For now， you can。

Forget about C for a second for a moment， at least。Let me try this。Okay。😊。

What you would see is for each of these states， A， B， and D， the next state is the same。

 it's A and B， and the outputs are also the same。So at this point。

 how you can rewrite this diagram is the following。有C。

And you start with C on a reset and let's say we have some state x in a new state x。

 which basically abstracts away A， B and D， and what happens is C goes to a or in this case x when you have a zero。

It goes to。Again， this new state X。Am I doing this correctly？Oh actually。

 it doesn't matter to draw this out you could just。Use don't care conditions， let's do that。

And you can interrupt me anytime if you have questions。Or if I don't explain this well。

 which is also fine。And。You have the output， okay， and。

We saw that we can decompose this down to two states。Let's say the new state is called x。Okay。

 and we retain the sea。And you have your inputs， 01。

01 when you see for this state x and an input of zero。

You stay in the same state and you have the output one。Your output is inverted for all cases。

 let's fill that out first。And now when x sees 1， it also goes to x again。

because we see that the states A， B and D are pretty much the same， they're equivalent。C。

 when it sees a0， it goes to a， in our case， that's x， C when it sees1， it goes to z d。

 which is also x。Right， so you can see that always the next state。

Is x irrespective of what the input state is。Which means that you can rewrite this as following if you have the reset。

 you go to X and you always。Go back to x irrespective of the input。

The only thing that you do here is you invert the input。To compute the output， you invert the input。

That's the FM。At least the first part of the question。Any questions here？So it's very clear again。

 perfect。So， the next one。We have。A little bit of。A bit more fun question。

 So you were supposed to design a more FSM。 And the definition of more FSM is that。

Every output that you generate will only depend on the current state。

 essentially the output is only a function of the state。It doesn't depend on the inputs。

If it was a media FSM， it would depend on the state and the input。

The state machine would have just one input and one output。

 and the goal of the FSM is to detect a stable transition in the input signal。

From a repeated zero to a repeated one and the definition of a repeated zero repeated one is this one right here。

 so the output logic output should be logic one only when the input sequence of00，11 is observed。

So you have a repeated zero followed by a repeated one。And in all the cases， you see。An output zero。

Then you also have the information that when the circuit is reset。

 your state machine should assume that the input signal has been high for a long time。

This will be key piece of information when we start drawing the FSM， but for now。

 let's keep that information as something that we have to use。

Draw the state diagram and explain why this works and your state machine should use as few states as possible and each state should have a precise definition。

You can see that here are four values here。About four bits。

Which means that you can have up to 16 states。Correct。

This is the brute force solution and this is not what we're looking for。

 we're looking for the fewest states possible。And what you will notice is that you can think of this in a sequential manner。

Let's start with putting up all the states that we can think of and we will come to the solution。

Clearly we need the state that identifies 0011， so clearly one state is going to be called's let's call it as 011。

That's stick to the nocl and the solutions。You get to this state and of course。

 when you're at the state because this is a more machine。

You have an output one and we write the output as part of the state because again， it's a more refer。

You can only get to this state when you've seen the sequence and I will write this here as scratch。

 when you've seen the sequence 001。In the recent past， if you've seen this sequence。

 it doesn't matter what exists here or here if you've seen these three in the past。

YouAnd you see another one you can get to the state， so let's introduce that state and we call this。

C is1 and here is going to be in output zero and you get to this state。When you have an input one。

Good。If you have to get to this to。You need to have seen two zeros， which means you need。S X。

 and let's call it。0，0， the output again is going to be 0 here， and we will have a 1 as the input。

To get there。What else can we build from here you this is when this becomes very useful here。

 so when you have a reset your machine should assume that the input signal has been high for a very long time。

 which means that the last input that you see is one when you enter the research stage。

 so definitely one state has to be something of the sort of。です。

And this is what you enter when you have a reset signal。So this is， let's say， the fourth state。

What else can we fill， let's look at as 001，1 what happens when I see a one after this or a zero after this if I see a one after this。

After， let's say001，1 if I see。1。This is no longer an interesting pattern for us because we can't get to 0011 and if you see 00110。

 again， this is not an interesting pattern because what you want to see is 0011 in the sequence。So。

In the case that you get one。After this。You go to the reset state， the state that you enter。

 the x6 x1。You also need another state， which is corresponding to this one where let's say you have a one and a0 at the end。

 and this is what we will create here， the Sx。1， seal。Is that correct。 That's correct。

 And this will be， again， an output 0。 and you get here。When you have an input zero。

Has everyone folder it until here， if not。You can ask me。Questions， okay， good。All right。

 so we have these states。 And now our job is。To complete the diagram。At this point， when you see 10。

If you see a one， you go back to this state because this is the last one， right？

This is where it goes when you have a one。 If I were to see see a0， then the sequence。

Now becomes very interesting to me。Because you can you will have a zero and a zero following it so it goes to the state on a zero if we haven't handled what happens when you see a zero here。

 what happens when you when you see a zero here well we're still on we're still interested because if this follows if the zero is followed by another one then you can go to this state so let's。

Stay put here when you see a zero。Okay。We have en what happens when you see a zero here。

 so when you see a 001 and when you're in 001 and you see a0， you end up with10。

 which means this is the state you go to and you see a zero。

We've handled all possible scenarios here。呃Cs cures。其实。Not here。 We have only。Well。

 we don't have any exit points here so what happens when you have one well。

 if you have a one you are still locked in here basically you have the same terminating value。

If you see a zero， then you go to this state because you've created a state for one zero specifically。

And that's what and that's the entirety of the state diagram。

If you can walk us through with your writing as to what each of these states mean。

 you will have full point。That's pretty much the FSM question。

Any questions if you're confused about something， please ask me。

It does not look like anyone's confused， okay。So that's the second question。And now we move on。2。

A difficult but very fun question。So for these kind of questions。

What you want to be wary of is the huge amount of text。Should not be looked at first。

You should look at the questions。Maybe side by side would be helpful so and let's do this。

So this is on vector to processing。What you see here is your instruction set， you have an ISO for it。

You have a bunch of assumptions。Let's not worry about the assumptions for now。

 so what you're supposed to answer is。Three questions， I believe。So the first one is。

What should be the minimum number of banks to avoid stalls while executing these two instructions。

 so clearly we need to focus on what these two instructions mean。

and calculate the minimum number of banks for every stride we need to understand what the stride means here。

 okay these are the two things I need to understand for this question。the second one。

Translate the following loop into an assembly code that can be executed in the least possible number of cycles in the previously described vector machine so you have this code。

And we have an instruction set here in the main question。So they basically want us to unroll this。

 let's say see program into this set of assembly instructions。

 and you've seen something similar in the DCL labs where you wrote assembly basically。

But this is with vector instructions， that's the only difference， the third question。

What are the number of cycles the previous， the previous code being disc code takes to execute in the processor that we describe and again you have some assumptions okay？

So these are the questions that we need to know about we need to solve and for the first one we need to understand what the VLD is。

 what VSD is， and what do they mean by stride here。VLD， so VLD is described by one opera， well。

 two operas， VI and the number a。hi means something here and its latency is 50 well it says 50 row hit 100 romus pipeline at this point this may mean nothing to you。

And this is what the description of the instruction is like， basically so a is the address。

 so based on the address you give， you load the data from the address into the register VI。

 which you describe here in instruction also。This something similar for VSD essentially you store data that is in resist VI into this location。

 but you need more information than that to understand what's happening so scan let's scan the assumptions and see if we can find information so we need information about VI what that means。

And what did they mean by Roheads， slow misses， pipeline， eta？So let's start and scan。We have。

Something about VLD here。Do we have something else？We have some latency here。

I think that then the registers， okay， let's start with this。There are eight vector registers。

 you have v0 to v7 and the size of a vector element is four bytes。4 bys，32 Bs。Doesn't matter。

Um what else is interesting， this one， the main memory is composed of end banks。

 you have N banks in the main memory， they don't describe what N is。

And each bank has a row buffer of size 64 bits， which basically would be 8 bys， or in our case。

 two vector elements。Does everyonet follow until here？Good。

All roads in the main memory are initially closed， so you have to pay the row access penalty。

 basically opening of the row penalty I mean。The memory is byte addressable。

 which means that you can access one byte at a time。

 essentially address a would correspond to vector element zero address plus4 would correspond to vector element 1。

Because it's byte addressable and every element is four bytes。

They're stored in the four by the line manner， the first element August starts at the beginning of the row。

 great。This is also interesting vector element store and consecutive memory addresses are interleaved between memory banks。

 so we saw here that we have N banks right so I mean of course they described further so if you have a vector element address a would map to bank D。

A risk element vector element at a4 a plus4 word map to bank B plus1 modular N。

 essentially the next bank that you have in the set of banks。And may not necessarily be a power to。

I mean， this is additional information that you don't need to worry about right now， I think。

Then they describe what the latency means， the latency of accessing memory is 100 cycles when you miss in the row buffer。

This is what they're talking about here， 100 room is。

50 cycles when memory request hits in the robot buffer， and this is what it is。All right。

 and every bank has a single read and single write port so that each load and store operation can be performed simultaneously。

You have one functional unit for VLD and a separate functional unit for VSD so you could let's say。

Do them parallel， but you cannot overlap them for different vectors。That's again， described here。嗯。

And then the last they describe about vector masscular just which。

Looks like we don't have to worry about at the moment。Co and of course。

 stride I think they don't describe here because it's part of the lectures。

 so I assume they assume that you're aware of this， but if you're not stride really means。

What is the distance between consecutive elementss that you access in your program？

So if you access memory。A。Memory a plus4。And then memory a plus8。This is at a Str one。

If you were to do this。Is that right， yeah， a plus8 April 16， this is this is at a stride of two？

Okay， does that make sense？Okay， looks like it makes sense。Okay， so the question is。

 what should be the minimum number of banks to avoid stalls？

When you describe the minimum number of banks to avoid stalls。

 it means that you are trying to send a request to the D in every cycle。

 essentially you don't have stalls and you once you get data from the memory。

 you can issue another request， essentially the data path is not bottom like by have memory aes。

And what you can think of here is try to start with1，2，3，4，56，7，8。

 assume different strides and think about how many banks you would need。

We know that this is the penalty that you pay on the room miss。

And why we should consider the room penalty is because。

They described that the Dm is first entirely closed。

 all rows in the main memory are initially closed。Okay， so the first axis is always going to be as。是。

And。So let's say we have a st one， then the banks that you would access would be bank。

Let's start with。 let's should， how do we index it， Let me。Follow what to do， Sir。Okay。

 let's start with zero， so you would access zero，1，2，3。And so on， right？

U the memory access latency of this is 100 cycles because it's a room miss， which means。

That the data of this is going to come back at some point in the future， and that is at the timest。1。

0，0。Which means that you can only send another request to the same bank at cycle 101。Therefore。

 if I were to have 100 banks。I could get away without incurring any stalls。Does makes sense， cool。

Let's take two， so B is we can solve zero，2，4， six，8， and so on， and at some point。呃。

You will have 100 and this is going to return back with data in cycle again， 101。Well。

 you can send another request to this at 101， which means that after you do 100。

You want to be able to request one again。So that you use all the banks that you have。

As much as possible。And then at cycle 101， let me write 100 here somewhere in between。1。

 and then3 and then 5。So that you can encycle 101， this is cycles。In cycle 101。

 you can again go back and access。0。Is that correct。Maybe not。2， to one。100。

 And then you start with one and 3。5， you end up with。Yeah， you need， you need 101 as well， right。

 sorry， I will do this again so that it's clearer。TheWhen you have stride of two。You start with zero。

2，4。And you go up， let's say， until 100， I'm arbitrarily choosing 100 at cycle 100 in the future。

101 sorry。You can send a request back to zero。And here in the meantime。

 you want to send requests to one， three。5 and you keep going。

And this would take you a grand total of。51， will this be a grant total of 51。Thanks。😊，And sure。

You end up。It going be 51。Want to give for faith。Five and five yourki points coming 50。呃。No。

 I was right。And you one，2， three，1，3，5 and you end up with 101 at the end when you issue for 100。

 and that's when you can issue an access back to0 in 102 actually because you want to go to 101。

So that you utilize the entirety of your bank the entirety of your bank parallelism and what you will notice is that when you go to Stride three again。

 you will notice a similar pattern to this。Striide4 will be a similar pattern to this。

 essentially all the even strides will require 101 banks。All the odd strides would require 100 banks。

Let me show you a quick example for this， so let's say have the bank access order is going to be something like this zero。

You're going to have three。Yeah。6，9。 and you keep going and you will end up at。9 you he。

Then you will do one in， well， should it be 99？Yeah， I think it's fine one and then。

You would have 100。And two， you would end up。At 98。

This would have covered up the entirety of the 100 banks， and this will take 100 cycles。

At that point， you can issue an access to you again。And this again covers up all the100 banks。

 you hide the entire 100 cycle latency off。Accessing zero by issuing access to other banks。

So what you will arrive at is that for all odd。Stras。You would need 100 banks。And for all even。

Sttraidedes you need。101 banks。And that's how you could solve it one possible way of solving it。Yes。

 please。诶仲之。For this one for the artstr。First and the third， this one and this one。Ten。

 is that what you mean？嗯嗯m哼。あ oneだ。You are right。I should be taking 99， right？Yeah， you're right。

 you're perfectly correct， this would be 99 because you count zero for this 100 cycles later。

You can issue an access to the same， you're right， so 100 banks。

 but you issue a request back in cycle 100。You're correct， sorry about that。Okay。

If that didn't make sense， you can ask me， I will repeat。Thank you。And。So the second question。is。小。

So and this is where okay， so translate the following loop into assembly code that can be executed into the least possible number of cycles in the previously described by the machine so you want to write assembly code for a C program what you really need is the instruction set and we have the instruction set here I'm going to bring this back here。

IThink that's visible now。O。So you have a for loop。

 it starts from 0 to 45 and you check if the element in a is zero， if it's zero， you write B to C。

Else C is basically the multiplication of A and B along with a divided by two。

 you add them up and we have these instructions here in the ISA so let's look at what instructions we have understand them well and then come back to that。

So the first one is set。And what this does is。You have two opera， VST and a number n。

 it takes one cycle and what you can do with this is you can write n to VST VST in this case is the vector strideide。

Register， essentially what is the stride that I'm going to use to access the memory for particular for whatever array that you want to access。

The second is again， a set。And what you want to do here is well what outputs you have here is VLn and the number n and what you do here is you write the value n to the resistor of VLN。

 which is the vector length resistor essentially how many elements in the vector are you going to operate upon the next is LDM which I believe is an expert description on here。

You have one opera VI where you write the least significant bit of VI to this particular register V MSK。

 which is the mask。Register and we have something about master， so let's look at these two。

 the first one。LDM moves least significant， but the LSP of each vector element。

In the vector register VI into the corresponding position in VmK， and this takes one cycle。

Essentially， this is to build up a mask upon vector the vector lens， so let's say you have。

Vectctor length 16， the mass registeror is also size 16。

 but you can make sure that let's say if all of them are zero except last one one。

 then the arithmetic operation that you're going to executed will be executed only on the mast。

Element in the vector registeror that's what the that's what the masking instruction helps you do we have already seen VLD and VSD。

We have Vmo。Which takes 10 cycles to perform multiplication， It's pipeline。

We add five cycles pipeline， v shift right， you can shift right by one and then you have V not。

 it's performed a bitwise not。Of VI and restored back into VI。And then you have the V compare if0。

 so if you compare Vj to0 and if it is zero， VI will be stored with all ones or all zeros。

It's to compare if the values are heroes are ones。All right。

 so this is what we have in the instruction set and。

All of these instructions are going to be useful for us to write down。The assembly code。

 So first we noticed that your for loop。Goes from  zero to 45 and it's doing so in steps of one。

 so your stride。Is one and the vector length is going to be 45 minus 0 plus 146。

So you have 46 elements in the vector register， so the first things that you would do is you would set VST。

 the stride。To one。You would set the vector length。To 46。

 these are the first two instructions that you will run。

 You configure the the vector machine for the court that you're going to execute then you need to。

Check AI conditionally， which means you need the data AI first， and that means that you need to load。

Lowed the data stored in the register above stored in the address that a points stored。

And let's assume that the location a the area A is presented location A， which yeah and。

The syntax here is the number a here is address and you want to store them into VI that's arbitrarily choose to do this in。

V1。And this is going to take some time， right， because you're loading 46 elements。Inter V1。

Then the next while。While this executes， you can fetch the data corresponding to vectorta B。So。

 let's do that。We will load that data into B， we load that data into V2。

We've loaded that as well and once the data is available for a。

 you can conditionally check the contents of V1 and to check and what we want to check here is whether they are zero and we have the perfect instruction for that。

We compared zero and to do that， we can compare。And we need a VI and a VJ VJ is the input that we want to compare。

 which is going to be V1 and let's store this into some other register V3。That we can use。

To perform computation for this one and this particular one。 First。

 we will take the true condition if， if V 3 contains。Once。

Which is basically the scenario where V1 contains as zero。

Then you would basically copy B directly into C。Correct， so we need to set up a mask。

That matches this compare the compared data in V3， so what you would do is for the mask， you do LDM。

So you do perform LDM and what you can yeah， you and VM is an architectural register so you can just do。

LDM V3， and this will set up the mask register after which you can perform。

The store operation which stores BI into C。Is that correct， that is correct？And yeah。

 you will and for the store operation， you have the register you want to store and then the address。

 the register that we want to store。Is B， which is in V2。And this would be stored in the address。C。

Okay。😊，Once this is completed， we want the else condition and the else condition。Again。

 can be derived from V3 iss essentially the bitwise knot of V3 when you enter this particular。

Part of the condition。And you can do that by doing the not。

 and you just basically provide the same register and the same register overwritten。

And that compare register is V3。Then we can again set LDM， set the mask for disturbed V3。Yeah。

 and at that point。We can go ahead and compute this。

The first step here would be we should divide AI by two。And then multiply AI and BI。

 and then you can sum them up and store them into C。But to divide by two。

 we don't have a divide instruction， what we do have is a shift right instruction。We can do VshHA4。

See。😊，The input cure is going to be a， which is in V1。Okay。Then we can multiply。

 which is mo that's stored it into V5。The multiplication takes two inputs Vj and Vk。

 which in our case will be A and B， which is V1 and V2。

 the two inputs here that we loaded in V1 and V2。The result。Of the two parts are in V4 and V 5。

 So this is v 5。 This is V4。 Finally， we add these two。Let's store into V6。

 and that's going to be me 4， V5 and at this point。We can store the data that's present in VD。Oh。

 it's for V6。Into sea。Does this make sense？Or not。Okay， I'll assume that made sense。Good。

And the last one。Okay。Is。The following question， well， that's the solution。Okay。

 so what's the number of cycles the previous code takes to execute in the vector processor described the question？

You can assume A and beer are in different rows， and the machine has eight banks。

And the rest of the machine is CMS part B， our code from the previous question is。Here。Okay， so。

Oh sorry here， so we need to execute this code and we need to find how many cycles this would take to execute。

And we can and to get the number of cycles for this particular code。We can look at。嗯。

The latencies that we have here。So every instruction has its corresponding latencies。

 in some cases they're pipeline in some cases they' are not pipelined。

And they don't necessarily need to be pipeline as well。

So let's make a note of all the instructions that we would need to execute。So。We have。

 I will copy these first。 So you have this set。You have VLD。You have VST。Me compare。We not。

Me should write me more。And we add， I think， an LDM。These are the instructions we have。

And they take the following latency， so you have one。

VLD would be 50 or 100 depending on the bank's scenario， same goes VSD。Compare is four pipeline。

We not is for。Pipline。We shift right as 10 pipeline， the multiplication is 10 pipeline。

 we add as5 pipeline and LDM。Is one。Okay， so we don't need this anymore。We do need。Is。啊。

That's right here。So。Clearly， the answer would strongly depend on these two parts because they're the bigger values。

嗯。And。What's also interesting is。That A andP are in different roles。

 which means that they will incur row conflicts always you have。46 elements that you need to access。

And aid banks。And we also know。From。Suret。That consecutive memory addresses are interleaved across different banks。

 which means that address a goes to bank zero address a plus four would go to bank。One and so on。

 okay？呃。And。Let's let's draw what the scenario would look like at each of the banks。 so we have。

The seven banks。Okay。The first axis is always going to be a miss because everything is precharged。

You have a miss。And then you can after one cycle， you can issue another。Request to B1。

 That's also going to be a miss。You keep following this with misses and I'm going to。

Shorten this and write this is M。Okay， after the miss and the first one， you'd have a hit。

Because the row is already open， right？And this follows here as well。However， we know。

That our row buffer size is 64 bits。Which is really two vector elements。Therefore。

After a miss and the subsequent hit。You will have to access a different rule。

Which means that you will have anonymous miss for all of these。And I will。Fill it like this。U。

In total， at this point， we've accessed eight times 324 elements。But we need 46 elements。

Which means we can keep extending this until we complete。46。Right。

 we're going to have another set of misses because this is。32。Sure， we would have。

40 memory access is done。And this will be 41， 42， 43， 44， 45。And 46。Okay。

Your memory access latency for the VLD instruction highly will entirely depend on the longest running。

Fetch wrongest string data fetch from the different banks。So B0， let's say， starts at。Time zero。

 it will take six memory aes and it will be done here。The longest spot here really is。

The fifth bank because it needs five cycles to issue its first load。

 and then you have the six memory aes MH MH MH。So。Every V load is going to take。5ve。

Plus three misses plus three hits， which really is 5 plus 300 plus 150。

 and that evaluates to 455 cycles。And this will be the same for store。Because for DM。

 D axis levencies are the same。So weloads and V stores again， we have 455 cycles。And at this point。

 we can start drawing out the timeline of what the instructions would look like to find the total number of cycles that we need to compute。

The court that we were given。So， let's start with。呃。The two set instructions。

So you can start with a set instruction first， it's going to take one cycle。

 then you will have another set instruction， and then you have the VLD。And。

The question also describes that the processor has an in order pipeline and issues one instruction per cycle。

So as long as you don't have an instruction going to the same functional unit。

You can keep issuing instructions。In the case of the VLD。

You need to issue 46 instructions because you're fetching 46 elements。

 but it takes much longer than 46 cycles。好。So this is what。

Assume let's assume that this is what 46 cycles looks like and it takes a while for the data to come back。

And unfortunately， you cannot issue any more requests in this period。

 in this blankedout period because。The next instruction is again， a VLD。

Which goes to the Dm banks and you will in conflict。So the next VLD needs to wait。Here in this。

 let's say again。Let's call it。this， yeah， this is going be 46。 gonna be 46。

 This entire period is going to be 4，55。And again， you have another。

Flank or period where you can't send any other memory requests at least。For 455 cycles。Okay。And。

After the wheel the instruction。You have the we compare to zero instruction。

 which relies on two inputs， well， it relies on one input v1 and the data for V1 is available already at this point。

So after the  46 cycles have been spent， you can start the we we compare instruction and the we compare instruction takes four cycles to start off and then it pipeline so this is the four cycles it takes to start this is we compare0 and then it's pipeline for 4 45 cycles and it will be hidden behind this because this is 455 it's going to be much longer。

Anyway。After we compare zero you have the load M and load n takes one cycle。

 so load M is also nicely hidden behind the memory axis latency。

Next you have the V store now unfortunately the V store cannot go ahead until the load M has completed because the DM banks are under usage。

So。The v store starts somewhere here。Again， you have 46。Cs。

And it's going to take some more time beyond that。Before you can issue other instructions。

We not realize oh sorry， yeah we store and we not re on V3 which is again already available so you can hide it behind this portion here between the portion where the memory banks are busy。

BO takes four and its pipeline， which means you take， let's say this portion here。

 it's going to be four。It's going to be hidden behind the latency， the pipeline。Then you have LDM。

Which again， is going to be hidden。Behind the various latencies。We shift right。

Relies on V1 and V2 both the which are already available and they store the data MV5 this again you can successfully hide。

Behind all the latency of the restore， this is about 455 minus46， let's say this is 40，9 cycles。

We not would take four pipeline， which means around。4 plus 46，45。This would be 49 cycles。

This takes this is hidden behind the Vnot， so we don't need to worry about it。

V shift right is also going to be mostly hidden behind the we knot again we don't go beyond the 409 cycles。

 essentially that's what I'm trying to convey here。We mall。

We add are similarly going to be hidden behind this portion。Because 409 is very long anyway。

At that point you need to issue another instruction the Vstore to finally store the computed V6 and for that you need to wait until this is completed the right from the previous instruction and that is again another 46 cycles。

Of instruction issue and then you hide， well， it takes time for you to write all the data， the banks。

So on the critical path， you have this set， the two set instructions。The VL D1， VL D 2。

 we store  one， and we store 2。 And that's3 the result。 So the total number of cycles is。

Set one is one second set is also one， and then you have two loads， two stores。

 each of which are 455 cycles times four。And this， I will not do the math。Compututes to 1，8，2。

2 cycles。Sorry for my bad handwriting here。Yeah。And that's how you compute solve this problem。嗯。

Any questions here？Or was this clear。Okay， perfect。 and that completes。To processing Os well。好。3的。

Should I announce it here as well？Yeah， so we will have for all for everyone on YouTube and Zoom。

 we will have a 10 minute break and then we start again。Okay。Hello， already。Amoidible。Okay。对。Okay。

Yeah。Should I start。对谢。Okay。Hello everyone， I'm Hershita and I will be presenting three quots today。

 so let's start with the first one that is Boolean logic circuits。😊。

So yeah so let's first read the questiont during your job interview you are asked to design a combinational circuit with the four bit inputs aBCD as you can see here in the truthth table so a is the most significant bit and D is the least significant bit and two1 bit outputs。

啊。Is it fine no。Okay。And you have two1 bit outputs， Fb and G3。

And you are given the value of each output is determined as follows so for Fb the output of Fb is one only when the input4 bit number is a fibonacci number so as you know that we can calculate the fibonacci number as the sum of previous two numbers。

So we will do it and second the output g3 is one only when the input forward bit number is greater than three so here as we can see in the tooth table this is written in the ascending order so we can just write the numbers。

So let's first fill G3 because it's easier so G3 is one for whenever the input for bit number is greater than three。

 so that is for all of these numbers G3 would be one。And for these， it will be zero。

And for Fibonacci whenever the number is a fibonacci number then the Fb output bit is1 so lets write the Fibonacci series lets start from0 we are given f of0 is0 f of1 is1 f of two with be the sumation of these again one f of3 would be summation of these two two。

And then three， and then5，8，13。21 we don't need to go beyond that because here we only have till 15 so0 is a Fibonaology number so here it between be1 and same for one。

For two for three， so four is not a ebonoology number so it's zero for5 it could be1，0。

0 and again for eight it would be1 and here zeros。For 13， it would be one and then rest zeros。

So now you fill the missing entries in the truthth table as you were asked in part A and also you are asked to express the output F in the sum of products representation。

So for the sum of product representation， you will pick all the one output bits so you can write it as。

O。So。A bar， B bar， C bar， D bar for the first one， and then here。😔，A bar， B bar。 C， bar， D。A bar。

 B bar， C， D bar。And then A bar， B bar， C， D。Then again， for this。😔，A bar， B， C bar， D。A B bar， C。

 bar， D bar。And then。ABC， bird B。So yeah， I think everyone every Tom is done。

 so by this we are done with our part a of the quot。Let's move to the second one。Okay。

 so in the second question you are asked to simplify thisb expression that you wrote here。

Using Boolean minimization rules and show you your work。

So let this is very easy like we can start with taking the common terms out from this。

So we can see that a bar and B bar is there in all of these four terms so we can just take this out。

And it would look like C bar D bar plus C bar D plus C， D bar plus C D。😔，And similarly。

 for the second one， you can take。😔，A bar and sea bar out。 It would be。B， D plus。Sorry， I think。

It is not there。So。Y。😔，You can't take this out。 So this is， this will be there。😔，But from here。

 you can take。😔，Just a second。Okay， so this is AAC bar and A bar。

 so here you can take the AAC bar out and B bar D bar plus BD。

So you will have this and this term would be one as we know。

 because it has all the combinations of C and D， so you will have。A bar， B bar， and fun。Plus。A bar B。

 C bar， D plus。Azeber。Just。And。B8立8 plusB。So from this expression， you can again takezebar out。

So you will have a barB B plus a。B bar， B bar， plus A baby。So if you optimize it further。

 you will get a bar B bar。😔，Plus， be bar。c d。😔，一班媳班地班。PlusB C0。

So this will be the final optimized expression that you will get。Does anyone have any questions？

I think this would be here。And for the sea part。You find this simple representation for the G3 output by using only two input na gates。

So again， you have to show your work step by step， so we haven't written the expression for G3。

 so let's write it first。Let me put it。This way， I hope you can see this。Yeah。So for G3。

We will again， write the some of the product form， and。你讲。So a bar， B， C bar D。

 I will just write it very fast because we have to take all of these values。And then A， A bar， B。

 C bar， sorry。Me。呀A820。😔，A bar， B C bar D bar plus。你包二逼。😔，Cbar D plus。A班BCD包老。ABCD plus。AB bar。

 C bar， D bar。Plus a。B包2C包2D。Does a B R C D bar。老 a。B bar C。Plus a。BC bar里 bar。😔，Plus ABC BD。Plus。

A B C D bar plus a B C so you will get this longer expression which will have 12 terms。

 so if you optimize it similarly using the approach that we discussed in the part B so I will just discuss the important part here so after optimizing it with the same technique used in part B you will end up with a plus B。

So the crux of this caution is that you have to represent the output using only two input na gates so how will you convert this form into two input N gates so since we want not because Nant has not an end so we can start by taking the n of this and if we write then these two are equivalent terms and you can also write this as the complement of a like this。

So you can also write this as this， but now it has two noded gates but we do not have any node gates we only have9 gates so you can also write this a bar as。

A into a， the whole bar。 So similarly， we will write here。So now this is we will need three。

 two input nine gates。One this， one this and one for all of this。

 So this is how the part three would be solved。Are there any questions？Okay。

I think this is the simpler question， so I will。Now， move to another portion。Yeah。

So the next question that I will discuss is the performance evaluation。

So let's first go through the quot。Multicycle processor P1 executes load instructions in six cycles。

St instructions in six cycles arithmetic instructions in two cycles and branch instructions in two cycles so consider an application a where 40% of 40% of all instructions are lower instructions so let's assume that we have total of n instructions out of which load are 40% so04 of n。

And 40% are load， and then 20% are store instructions。 so store would be0 to n。

And then 30% are arithmetic。And 10% of instructions are branch。And we are asked。

 what is the CPI that is cycles for instruction of application A and execute on a process of P1？

So CPI is the total number of cycles。By a total number of instructions。

Now what will be the total number of cycles so we have all these instructions so let's say first start with load so we have 0。

4 n load instructions and each load takes six cycles。

Now store 02 and store instructions and each store takes six cycles。

Now arithmetic point3 and arithtic instructions and each takes two cycles。And then。

Point1 and branch instructions， and each takes。Again， two cycles。

And the total number of instructions would be n。So if you solve this。

 I will not do the math if you solve this， so you will come out with a number 4。

4 so this would be our CPI for。B1， process of B1。I hope it's clear。O。

So second part is totally same we just have different parameters so a new design of the processor doubles the clock frequency so I think we will underline this because this might be needed in the later parts and however thetens of all instructions increase by four cycles so here for all the instructions it has become now 10。

Den。嗯，6。6。We call this new process of P2， the compiler used to generate all instructions for P2 is the same as for P1。

 thus it produces the same number of instructions for program a。

And again we are asked what is the CPI of application A is the same application that was in part a when executed on processor P2 and we have to show our work so again we will use the same approach like now we will just change the cycle count I will do it very fast because we don't have much here。

And similarly， point to n into 10 plus point。😔，3 n into6 plus point。1 n into6， divided by， sorry。

 divided by n。So again， if you do the math， you will come up with a CPI of 8。4。

So there was nothing new in this part。😔，I hope it's clear。Now in the C part。

 you are asked which processor is faster P1 or P2 by how much like what is the speed up and we have to show our book。

So the speed up。Is total number of cycles。Into the clock time。And to find the total number of cycles。

 we can do CPI into the number of instructions。In2'clock。 so this will be our formula。So sorry。

 this is execution time。Yeah， so let's calculate the execution time of process one and process two。

So execution time of processor one would be。The CPI for Pro1 is 4。4。

And the total number of instructions， let's assume n as we did。And the。

Plock time would be sometime P。Now for the processor two。

 let's say it's execution time two again the CPI8。The number of。

Instructions are again the same and so here the time so here as you noted in the second part we were said that new design of processor doubles the clock frequency of p1 so since the frequency is double so the time clock time would be half because frequency inverse of time so this was the motive of giving that so now we have both the execution time and we can do the speed up。

Let's say execution time1 by execution time 2。😔，And if you do that， you will get。😔。

That processor2 is 1。25 x faster than the B。So this is again simple。

 you just have to calculate the execution time of two processors and then divide them to calculate the speed up。

Are there any questions？Okay。So this is the last part。😔。

So here they have asked that you want to improve the original P1 design by including one new optimization without changing the clock frequency。

 you can choose only one of the following options so the first is ALU and second is the LSU so what does an ALU and optimize ALU which halves the latency of both arithmetic and branch instructions and an LSu and arithmetic load store unit which halves the latency of node operations and doubles the latency of store operations so what does half halfing the latency and like doubling it means so that means for we have to root for processor one so if we do the ALU thing。

等。😊，Yes， so earlier the cycles to execute and arithmetic instructions were two。

 but now they are halved。 so it will be。Only one cycle for arithmetic instructions。

And also branch instructions for branch instruction， it was also two cycles so for branch also。

It will be。还世嘅路。😔，And what will an LSU do？It will halfal the latency of load operation that means load can load will just take three cycles and double the latency of store operation that is store will now take 12 cycles。

So now you again have to calculate the CPI。So using the same thing as we used here。So。

Point4 and into2。😔，6 plus。2 n into 6 plus。1 n。😔，Into1 plus 0。3 and into one divided by n。

And this is when you do the ALU optimization。And when you do the LSC optimization， so CPI will be。

t4 n。印度。3 plus 。2 N into2。😔，滚。6是。😔，1 n into2 plus03 and into2 and then divide by n。

 so when you will do the math， you will get the CPI value for both and wherever the CPI is less so that will be that will be your choice because you want cycles per instructions to be less so this is how you do this。

So this was again， a very simple question。I hope everything is clear。有。I think it's， I， I mean。

 if you don't do the calculation， you will not get to the answer。 and you will have to。

You will have to tell which one you will choose and if you do the math after writing the formula then only you can say that this is the answer so you will have to do it full。

嗯。知得是。对，就是。第个。あしま。是。So， let's move to the third question。This is systolics。Okay。

So you are given a systolic array of2 by two processing elements。

 Ps interconnected as shown in figureig2 here， the inputs of the systolic arrays are labeled as H0。

 H1， v0 and V1。And figure3 shows the PE logic so this figure 3 shows the logic of each of these PEs。

 so let's say we treat it as a PE00 so here i1 is an input which corresponds to the at0 and an I0 corresponds to v0 and this PE performs a multiply and accumulate operation。

So it has an internal registered red and it does the input1 into input 2 plus the red value and then it also outputs the value as01 and00 so00 would be equal to i0 and01 would be equal to i1 so each of these ps will do this so this01 would go to then p01 if p is assumed that this is design of p00。

Yeah so figure three shows the PE logic which performs a multiply accumulate Mac operation as I already explained and saves the result to an internal resist stretch figure 3 also shows how each PE propagates its inputs this also I explained so we make the following assumptions for this the latency of each Mac operation is one cycle so to perform this we need only one cycle。

That is， if the inputs to the PE are available in cycle。

 C the updated register value will be available in cycle C this one。😊。

The propagation of the values from i0 to00 and from i1 to01 takes one cycle。

 so this also takes one cycle。And this also。And the initial values of all internal resists is zero。

 so this will be set as zero initially。Now， your goal is to use this sytolic array shown in figure two to perform the multiplication c is equals to a cross B where A。

 B and C are two by two mattresses。So let let's write this because to solve the further question we will need to see it。

 so let's say metrics a。A zero zero a zero one。气分之道。😔，一碗吗。😔。

And it has to be multiplied by the metrics b may 00。Bsy the one。B1，2， be11。😔。

Where a B and C are to cross two mattresses I recall that the multiplication so this is they are telling you how to do the matrix multiplication I think you all know this so as an example for k equals to 2 the calculation for c00 is shown as followss so let's say the result in mattress is c so c00 would be。

A0，0， B 0，0 plus a 0，1， B1，0。Again， C01 would be a 0，0， B0，1 plus a 0，1， B 1，1。😔。

I'm writing this because you will need this， so c10。😔，エ10。😔，B 0，0 plus a 1，1， B 1，0， and lastly。

 C 11。😔，A 1，0， B0，1 plus a 1，1， B1，1。Okay。So now we have to compute the multiplication in the minimum possible number of cycles。

 so fill the following table with each input element from metrics A and P in the correct cycle and input port so of the systo query。

Each output element for the metric C in the cycle and P that generates each output so whenever the output is generated like c00 c01 we have to fill it in here。

So part As we have to fill in the blanks only with relevant information and input cells left blank would be interpreted at。

So let's start so let's say this p00 has to calculate c00 p01 has to calculate c01。

P10 has to calculate c10 and P11 has to calculate c1。So to calculate c00 first we need a 00 and b00。

 so first we can pass a 00 from at 0 as an input so here we can write a 00。And as v0。

 we can pass v0 zero。You can also do vice versa like pass J 00 is v0 and then your table will look a bit different。

 but I will go with this。So in the first cycle， you can only do this。

And when these inputs will go inside the PE， so it will have a register and the register initially is zero。

 so it will become。Input 1。Into input 2。😔，Plus zero because it was initially zero。

So we didn't get any output out of these four in the first cycle， so we will leave these blank。

So next let's move to the next cycle。So， here。These in c00 would be propagated to p01 and it will calculate c00 c01 and rest litter and similarly this B00 will be propagated here and similarly it will also calculate the Mac operation。

Now what will be the new inputs in this cycle first now p00 calculated this now it has to calculate a 01 and v10 so as at0 we can pass。

A0，1。And as v0， we can pass B1，0。In this cycle this01 has also received an input from p00 so we will also pass another input from V1 so what PE is 01 has to compute so it has to compute this so it already has this and it needs this B01。

And it also needs a01 and B11。So in the cycle。As we won， we will pass。Sorry。

This will be 10 because we have to pass it here and it test to compute and this will be B01。

And as h1， so it has to compute c10。So a 10， b00， a 11 and p10。

 so here we will pass this a 10 because it already has p00。So no。

This P00 has all the output that it required like this from the previous round and in this round we passed。

A 0，1 and B 1，0。So this previous cycle Ra value will be added here and it will。Have the full C00。

So that will be the next cycle because this will take one cycle。

 this will take another one cycle so after two cycles p00 will have c00。Now similarly。

 now if you see， we needed these outputs， basically we needed eight inputs。A0，0， a0，1， a1，0， a11。And。

😔，B，0，0， B0，1， B 1，0， B，1，1。We have already passed。😔，A 00， B 00 in the first cycle and a 0，1， B 0，1。

 a 10 and B 10 in the second cycle。 Now we are only left with a 11 and B11 so which all。

Ps required this。 So C。So， this。B01 requires B11， so we will。So we will pass V11 here as V1。😔，And。

And these PEs require a11， so we will pass a11 as each one。So now we are done with all the inputs。

And no。This so here the operations that didn't require a11 and B11 would be done in this cycle。

 so that is C01。And c1 zero。And then， in the next cycle。We will have c11。 that will be a 10。

So this is how we will construct our table。哦， just question那个。So。This one， yes。Yes。

Shouldn't there did that sell be80，0 times？你关。So。这个。Yes。

 so if you want you can write it but I didn't write it because in the question they have asked you to write the full output when you get this so the output bits are only only c 001 c01 c10 and c11 so that's why I wrote only this but if you want to keep track if you also write a00 b00 that will not be wrong。

Yeah。傻嘅。Now， we have one more part for this。😔，So the question is suppose that the same systolic array from figure2 is used to compute the multiplication of two foureclo format mattresses how many cycles does it take to perform the multiplication assume that the register in a PE resets to zero immediately after an output is generated that is PEs can start accumulating for the next output element in the next cycle without waiting for an extra cycle to reset the register0 so you don't have to waste a cycle to reset the register zero that's what this says。

So we can do it with unit method so。In part a， we had two cross to mattress。And。It has8 inputs for。

For metrics A and4 for matrix B。Now in this case， you have four crossover metrics。

So you will have 32 inputs。16 for metrics A and 16 for metrics B。

So how much time did it take in part a for us to supply all the inputs to the Ps it took us three cycles right so here we can see that eight inputs took three cycles。

Then 32 inputs will take three into 32。By 8， that is 12 cycles。

So 12 cycles will be required to just to supply the inputs， so lets write 12。

So this is the first thing， no。When you had to calculate lets say C00 so you had four elements like four input elements were required。

 but now since it is a four cross form matrix you will need eight elements， I can write it。0，1， B 1。

0 plus a 0，2， B 2，0。Plus， a0，3。Be crazy。Now here we can see that you in the case of two cross two metrics you got the first output after two cycles。

 so when you had four inputs like basically you had to compute on four appearance then it took。

Two cycles after two cycle in the third cycle， you got the first out。Now you have eight appearance。

 so it will take you four cycles。And in the fifth cycle， you will get your first output。😔，And also。

 you can also see here that。After you get the first output， you need two more cycles。

To get the all the output。 So this trend will be repeated。After this， so first we can add。

So earlier we got 12 cycles。Now， after that。After。5 cycles。Sorry yeah。

 so four cycle on fifth cycle you will get then the first output and again two more cycles to get all the outputs。

So if you sum this， it will be 19。So here the answer would be 19 cycles。😔，F。Any questions。哦。直接早。

I think。For agency。包括。Yeah， so yeah so to look at it， I mean I don't have an intuition。

 but if you will calculate it， then I can show you the table here。😊。

So this is how the table will look so because the PE structure has not changed in this。😔。

So you can only supply like two inputs at time and again you can supply the same number of inputs so if the number of inputs have increased then it will take n into the inputs that you can supply number of cycles to feed in all the inputs right so that's why it is scaling this way if you can imagine but otherwise you can try constructing a table again and it will again take a lot of time but yeah this is how you can see but yeah you can relate it with how many inputs so you can feed and then scale it and if the PE structure would have changed then yes you would have to see it in a different way because now you can feed in more number of inputs so it cannot scale linearly like this way。

对。Any other questions。オケ so。That's for my site。啊。That。对。胃康。嗯。ok。Please one？Okay， good。对。

Can you hear me。So we're going to start with V line W。Should I just read this one a of it or just？对。

Description。Okay， so let's just run through this quickly。

So we have to compile some VLAW code by hand， this particular CPU has seven functional units。

Three load units， one store unit， one addition unit。One multiplication unit and one branch unit。

So the VIWU can only execute the instructions， the operations。Shown in table one here。

And the rib also shows the semantics of each operation。

All assembly operations have one cycle latency， we have 32 registered， that we won't need that。

The registers are read at the rising edge and written at the falling edge of the clock。

 and the memory is word addressable 1 word equal4 bytes。

 and the VLI W processor operates at one giggahertz。So figure one shows some C code you can see here。

 basically exactly。The loop that we are most interested in。

And also the associated assembly code for this particular C code。Register is R29， R30 and R31。

 hold the base addresses of the SQ code array A B and C。

And register R 0 is initialized with0 and register R 1 with one。So。My job here is to compile the。

Assembly code into VLAW instructions to schedule them statically。

So we're going to fill this table with how I'm going to do this， you have to see both。嗯。う。

To fill the this table with instructions showed here。So if you remember correctly。

 this machine has three load functional units and the first three instructions。Are load instructions。

 There are no dependencies between these instructions。So we can load them。

 we can schedule them at the same time。So we will have the load one ink here。

I'm not going to write the details of this because I can't fit it， but you should load。

And also the other load， this one。So we have a multiplication with R2 and R3 after that。

 but we cannot schedule this。Because this depends on the result of these operations。

 So we are just going to fill the rest of here this。With knobs。In the next step。

 these operations will have completed because every operation takes one cycle latency。

And we will be able to schedule the multiplication over here。

 so this operation goes to the multiplication unit。嗯。And the next operation depends on this。

 so you can see it's add R6 R5 r4， and we are calculating r5 here， so this cannot be。

This cannot be scheduled in the same cycle。So I fill everything else with knobs over here。After that。

 we have。The a add also depends on R5 because you can see it's add r 6 or5 or four。

So I'm going to schedule the ad here。And fill everything else with knobs。

St stores the result of R6 in the next cycle because R6 depends on the calculation of add。

Is the store unit need here。Store ink。And the rest are nos。

And we can not schedule the branch in the same cycle because this is a store ink。It increments are 6。

 You can see here that。R C it increments R 1。So that means that there is a dependency over these instructions。

And you have to schedule the branch in the next cycle， B and E， the rest are knobs。

So this is the table filled out。Let's move on to B。

 what is the ratio between the number of useful operations and the number of VIW instructions in your code？

A useful operation refers to any assembly operation that is not a knock。So here， as you can see。

It took us five cycles。To schedule everything。And。We had seven operations to schedule。

So the result here。Equals7 over 5。Yeah， that's it。What is the execution time in cycles of the VLIW processor when executing the sequence of instructions in table2 as a function of the loop counter n。

 show your work and this is very simple here。You know that each loop will take one，2， three。

 four five cycles。And it's going to repeat for I equals1 to I equals n I smaller or equal to n with an increment of 1。

 so it's going to repeat n times， so that means。That in cycles。This is。5。Times， n。Yeah。Sure。Better。呃。

Any questions on this question？彼子。So let's move on to the next one， which is about caches。

Consider a processor using a four block。LR U based L1 data cache with a block size of 1 B。

We are going to start with an emptyc。And an application is going to access three cash blocks with the following addresses 024 in the given order。

A malicious programmer tries to reverse engineer the number of sets and ways in the L1 data cache by issuing only two more accesses and observing the cache sheet rate across these two axises。

Assume that the programmer can insert the mal use accesses only after the above three axises of the application。

 so we are going to add one more access here。And one more axis after that here。

 And we are going to observe how this changes the cache heat or mis rate。

What are the addresses of the next two cache blocks that should be accessed to successfully reverse engineer the number of sets and ways into cache there may be multiple solutions。

 please give the lowest possible addresses that can enable the identification of the number of sets and ways。

 please explain every step in detail to get full points okay。So we have a four block cache。

And that means。That there are three possible cash configurations。

 The first one is the one way associated cash or direct map。

And this is going to have four different sets。So let's name this configuration a。And。This is set 0。

Set  one， set 2， set3。 The second configuration is the two way associative version of this。

 So we have two sets with two ways， two ways， each。This is configuration B。So this is set  zero。

 set  one。And we here we have inside here way， let's say， W 0， W1。This is one。

And for the other set also。Way 0， way 1。 Excuse my terrible handwriting。

And the other configuration is C， which is basically a fully associative cache since we have four blocks and it's going to be four way as。

So basically， this is just one large set。With。贵州。Way 1， way 2， way 3。 That's terrible。

And we're going to place for each of these caches。These blocks in here， so。In configuration a，0 goes。

 of course， to this is in binary 0，0， this is 1，0， and this is 1，0，0。

I'm going to add an extra bit in everyone one。We can distinguish。0 goes here。2 goes here。啊，意思。

With my use for a second。Okay。And 4。Is going to evict。0。And we're going to be left with for here。

So for B， zero is being placed here。Then two is going to reside in the same set as this one。

Over here。And。4 is going to evict the least recently used， which is zero。

And it's going to reside here。And for C， we don't have any conflicts。呃。So。Z is going to go here。

Two is going to go here and four can go here。For example。

So we have to find x and y so that we can distinguish between all of these。

There is no use in trying to issue any other memory accesses for addresses， other zero。

 two and four because these are going to miss anyway， they're not in the cache。

How we have to find this out is by causing conflicts between elements and then observing how the mystery changes。

So I'm going to start by issuing zero in every one of these cachees starting to store zero or load zero。

你舍得。呃 load。不清楚。And see what happens。So zero。Is going to conflict with four over here。

 Its going to evict it。So we're going to have， let's say。0， eing4。 I'm going to write this。

And over here。We 0， way 1， way，0， way 1。S 0， S 1。So， here。4 is also going to evict。

Zero is also going to evict。2， because it's the least。ARecently used one。And here。

 nothing is going to be evicted because this will hit in the cash。So I'm not changing this at all。

And now I'm going to issue a load on the two。And what is going to happen here？Is that。

The two in this case is going to hit。2。Ks。In this case。

 it's going to miss because it's not in the cache anymore。And here it's also going to heat。

So for this configuration， for the C configuration。We hit both on the zero and the two。

 That means that it has 100%。Herate in the cache。For the big configuration。

We missed both of the four on the。Thank0。On the the zero and on the two。

 So that means that we have the 0%。Htate。And for this configuration。

We had a miss on the load of zero。And the heat when we load it too。 so that means that we had a 50%。

Hitate。So you can clearly see that with this access pattern。

We can distinguish between the three cache configurations。

 and we can reverse engineer which one this is。Any questions？Yeah。对。啊。哇。Yeah。对。What do you mean。

我 by的。Yes， no， this is vital addressable。Is there not。Like it's a memory address of zero。啊。2月份。

So you load the zero byte of memory， then you load the second byte of memory and the fourth。Yeah。

Moving on to B， what is the number of sets and ways if the cash he trade observed over the two extra addresses in part one were 100% 50% and 0% so here I have to say there is an alternative solution here that uses zero。

And 4 instead of 0 and 2。But this is not the optimal solutions because we were looking for the lowest possible address。

That you can use So that's why here you have to fill in your results based on what you did in the first step。

 that's why we ask this。So let's say that we selected the0 and2 axis pattern。

So if we have 100% heat rate， that means that we have the fully associative cash and that means that we have one set。

With four ways。You have a 50%。Sherate， that means from the previous answer。

That we had the direct map cache。So， this here has。诶。F sets。With one way。And for 0%。

 this is the two set two way associative cash， so two sets。Two ways。And that's it for this question。

Moving on to C， is it possible to reverse engineer the number of sets of ways of the cache using two axises？

After the applications's first three axises， if instead of LRU， you used the MRU policy。

 so the most recently used cash block is getting evicted when you replace。呃， something。

And the answer to this is no。Why is it no。So let's go over this again we have。Our configuration A。

 our configuration B， our configuration C。You don't need any any ways here。

And after the first three axises were issued， this is going to look like four and2。

 this is going to be four。And  two into different ways of the same set。 And this is going to be 0，2。

And 4。So again， if you try using any other addresses zero2 or4。

 nothing's going to happen because you can these are all going to miss the two missing the cache。

 so you have to work with these three。If you issue zero or two or four。

 anything is going to hit here so you can clearly find out if this exists， but the problem is。

But if you try to issue zero， for example。Then in this case， zero is going to evict four over here。

Because it can only go into this set。Then here zero is going to evict four again because this is the most recently used。

So you cannot reverse engineer anything anymore cause。These look identical。

They they only have0 and 2 inside。 So the answer here is no， as we said。

 you cannot reverse engineer the cache with this。And the problem here is that eventually everything looks the same。

Any questions。And finally， there is the。Pretty fetchting question。So we have two programs。

 A and B that run on two different toy machines， M1 and M2 to determine the type of the prefeture used in each one of these machines。

The programmer observes。The following memory axis is in the program。

And we have the following metrics for coverage and accuracy and coverage basically is the fraction of the program memory axis that were correctly predicted by the prefecture and accuracy is the fraction of send prefec requests that are used by the program。

And this is the table， as I said previously。 There are three possible。

 There are three prefetures that we're going to evaluate here。 One is a stride prefecture。

The other one is a first next block prefecture with degree1。

 which fetches the next block after access to a particular block。

And then there is the fourth next block prefeture with degree1。

 which will fetch cacheline a plus4 after an access to block A。And here there are some assumptions。

 each professor has a large GF resources to detect and store access patterns。

Each prefecture starts with an empty table， each prefeture assigns only one prefecure request for each program access。

Each memory access is separated long enough in time so that all pre requests send can complete before the next access occurs。

No prefecture employs any confidence mechanism， the straight Precher will send a prefe request to address a+4 by only sync two consecutive memory accesses to addresses a and T+2。

So basically what we have three prefetures， two machines with these metrics。

 and we want to find out which prefecture each one of these machines uses。

There are two ways to go about this， there is the hard way， and then there is a smart way。

I'm going to show you。The hard way。Because。It's actually too much water。嗯。If I can find it。嗰手点啊。都好的。

😔，Yeah。Yeah。要不对。For the brief啊 here this。 Yes， thanks， sorry。So they hard way。

Is to take these axises， all of them。And evaluate every single one。

Of these prefectures and see what they're going to issue。

 measure the coverage for for both of these programs。And try to find it out this way。

You are going to calculate the coverage and the accuracy and eventually what you will come up with is that M1 is the fourth next line prefecure and then2 is the stride prefecure。

And that's the hard way。But the smart way here。Is to see that as you can accuracy for M2。

Is 499 out of 500， whereas for this it's 499 out of 501。So here and here。Of these prefetures。

Only one needs to wait for the second axis。And that is the stride refresh。So as you can see。

 the solution。The strip perfectfetureism too， you can see this here in the cave it issues one less access in total。

So that immediately gives you the result for machine two， for machine one。What are you going to see？

Is here that let's try the first next block prefecture with degree1。On program B。So this is going。

 we have access to b b plus 2， b plus 4， basically b plus even。

 so the next line prefecure is going to fetch always b plus odd。Right。B plus， let's say，2 K plus 1。

That's all， always。So if machine may had this prefecture， the next line prefecure， essentially。

We were going to see。And accuracy of zero because all these axises are even。

And this is a nod address， so it cannot be this。It has to be the fourth next block prefecture with degree1。

Does it make sense。公。嗯。There are other questions for this particular。Question， so。不든。哦。Yeah。嗯。😊，Yes。

 don't。So we have a question for VIW online。 No no， no， we're done we're done， okay。what you。

Yeah I'm just checking that you did all three because it was the first。我知道了。Yeah对。

Then now to be Athenbergster， so Athenberg is going to be joined online and solve a very low question for us。

Let seeAt Burke， can you hear us？Hello。Yes， great。Okay， can you hear me as well Okay we can hear you。

I she the skin。Not yet。嗯。Nice。I'll figure it out。 Yeah， no worries。Okay。诶。I joined the wrong zoom。

 so I'll correct that。 but I can see you。 No， no， I joined with my other device。😔，You are co host。

 which should be fine。Ming in progress。We can't hear you if you're talking。不した。I am not talking。

 I'm just， I'm still trying to find the correct zoling， sorry。I found it once。 I。

 I think I can do it again。Yeah。Okay progress。Now， I think it works。

So let me share my screen quickly。Can you make the other other bag also host。我。Whatever都 was。😔，Okay。

 I think we're good now you can try sharing。嗯哼。

![](img/a0c1679b2c3a30a40e53edc89b0fe349_1.png)

Yeah。Yes， we can see the screen。There go， okay。I will zoom in a bit he's zoom I think maybe you need to zoom it's too vertical right now。

That's better。 Yes。 It is too vertical Wait。 Now its。 It's good now。 yes，9 even better。



![](img/a0c1679b2c3a30a40e53edc89b0fe349_3.png)

ok。😔，So， yeah， we will solve a very long question from。2 years ago。I think。

And it says analyze the following very log module and answer the question。

Assume that the input has always this value。And that's9。And you're asked to。Find out。The。

 the values that the out signal gets in the。Following 10 cycles， basically。诶。So， here。

If you look at this circuit for some time， you will figure out。That it's doing。Something like a。

 it's outputting the。And the numbers in the Fi9 sequence。

I won't get into the details of why unless someone is someone asks a question I'll just。嗯。Basically。

 I'll be walking you through the answer。So here another key thing is。

That we won't output the Fibonacche sequence number。Until a control variable。

That's variable4 equals n。So if you look here， you'll see that n is always nine。诶。

But variable4 orf VAR4 starts from zero。Gets incremented every cycle。

So what we'll see is variable4 until。😔，Variable4 becomes 9。

And the first value that variable 4 takes is 0。So this will be like 0，1，2，3。

Because it's implemented by one every cycle。Until。It gets denied。And if you actually compute。

Variable 1，2， and 3 for9 cycles。 You'll see that。This。At at this cycle。Variable 3 will have 55。So。

That is， basically。It first。This part of the question。And as an explanation， you can。

You can put something like the module outputs the。the number in the Fibonna sequence and the index of the number is basically the cycle we're currently at。

Do you have any， do we have any questions about this？I can't see the room。ok。

So this is relatively easy。 And the second part of the。Very low question is。

A bit more more worthy you have。嗯。What's claimed to be a Chay P generated code。

 probably today this would look much better this was two years ago。

It says that a very long module that simulates a characters moment on a 2D plane。

 then we have like basically the specification of the module。

 it takes four inputs for four directions。And the grid that the character can move to it outputs the coordinates of the character。

If none of the direction inputs are set， this is critical to this question。

 the character stays in the same coordinate so it won't move。

And the initial coordinates are zero zero。And we have also a variable called Str that determines how many units the character moves in one step off。

If stride is zero， we expect or if stride is one。嗯。We expect something like， okay， if。Basically。

 let me just put it this way so stride this one。Input is left。 Let's say left is true。

 I'll say true what you understand what this means。If you're in0，0。

 we expect you to go to something like。诶。嗯。Like minus20， right， so you're skipping one great element。

All right。都。First， were asked to provide a choice for。Each of these bullets。And。

One line expression for three。So I'll do them one by one。

And I'll try to explain why I choose a certain option。So the first one is going to be an input wire。

Three bits。So this is a 3 bit vector why because。呃。

Each basically stride should be declared as an input because it's。

Specified as an input to the circuit。And。诶。This basically is not a valid syntax， right？

So you this this you cannot put anyways， so the only valid option really is C。

So that also tells us that the straight can be three pits。Sorry，20。And the second one。Is。嗯。This。

And the reason why that is is。Basically， the other ones are wires， but in this always block。

 we make assignments to this variable。X internal， Y internal。So that's this line， for example。

 in this slide。So for us to be able to make assignments inside they always block these needs to be defined as rags。

And the third one。I'll write the full。Expression。And then I'll explain。What it means。

So we're checking if straight。😔，Is not equal to0。😔，This three comes from here。Then it's right。

 if not as one， so its right cannot be。啊。0。And then。Why， because I mean， what does this do。

 it's anterernary operator， so it's like。If this is correct。电。You take this value。If it's not。

 then you take one。There's a semi colonlon at the end。嗯。And you have this。Same syntax。If you look。

In the first part of the question， so you could， in theory。

If this was your exam question this semester， you could look at the other question and get a hint。

And the last one。Is going to be a sign。Because。I mean， you cannot put nothing there。

 That wouldn't be correct。You cannot put equal the equal。

Or the equality check operator were let we didn't even cover this。So this is wrong， this is wrong。

 This is wrong。 Only this can be put there。 and that's the great thing。The have。Any questions here？

And no， they don't have any questions， atttleberg。Cool。

Then the last thing is asking if ChaCP injected any errors in this code。

 technically it didn't anyways because Cha GPT didn't write this code。

 but assuming that the question is correct。You should basically notice a logic error here。9ine，18。

The specification says that the character shouldn't move if none of the buttons are pressed。But。

 here。No matter what I do， unless the research signal is set。My character will move。In the X。

Dion in the extraction by some amount。But this shouldn't have happened。

And that's the sort of the bug in this code。And I think that's it。Any last questions from you guys？

Okay。Okay， thanks a lot at the Burke， it was clear。Thank you for your time。

Yeah so that was the last one guys， so we're going to now finish the session if you have any questions feel free to reach out to us send an email or yeah probably an email would be good。

And。I hope you have a good starting session and prepare well for your exam。

Also don't forget that we have plans and premiering of other problem solving sessions it's going to be happening next week from Wednesday to Friday。

 but they will also be online for you to see when you are like more convenient。Okay， thank you。



![](img/a0c1679b2c3a30a40e53edc89b0fe349_5.png)