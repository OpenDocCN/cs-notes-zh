# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p34 -34-  L30_ Problem Solving V (Spring 2025).zh_en -BV1iV1XBWEJW_p34-

![](img/a353d04db1d832c56a5c2639e9019930_0.png)

Okay， the next question is about Boolean circuit minimization。

 which actually usually they are the simple exam questions。So the first one is， so we are we need to。

Yeah， we need to rewrite this equation to make it only using NN operations。So to solve such question。

 usually。A good strategy is to use。Not， not。So we do not not。Plus。Sbo。A班 c 班。Yeah。Thank you。嗯 then。

So a bar， not not is a bar， so we can it is。a b。Dot C bar。That's a bar， C bar， and bar。

So we can actually。Write， rewrite this question and this part， which is C bar， A bar， C bar。

 And then we don't need to write C bar。 So we reach to。ba。Dts。A sea bar bar。

And now we can see that here we have a N operation， the overall is a N operation。

 but this one needs to be a N operation and for that， the only thing we need to do is，嗯。再说。

Any question？G到 easy。Support B。So we need to write the function formula and then try to simplify it with Boan。

Equations。So the function is。Based on the meanters that we have here。Is a bar， B bar， C bar， D bar。

Plus， abar。B， sea bar， D bar。Plus， a bar。B。C bar啲。Okay。A， B， bar， C bar D。lu a b。西ber啲。So。

You need to try， find common terms and try to factor them out。So we have a bar， C bar。

 D bar in both first two terms， so we factor a bar。



![](img/a353d04db1d832c56a5c2639e9019930_2.png)

B bar， Dbar。And then we have C bar plus C。It。忘记。A bar b。😔，C bar d bar。A bars， B， C D。Yeah。

You are right。This is a B bar Ci D bar， a。B。A。B媳吧地板。Yeah。Thank you。So here if we factor a bar， B bar。

 D bar。没有。A bar， D bar， C bar。Then， we have。B bar plus B。So we can set them this two term。

Here we have A bar B， C bar D。And we can find similar one。😔，Yeah， these two。So。B civil D。

Reish to this one。And also， we have。This two term。嗯。A c bar d bar。B bar plusy。So these items are。

 these are one。So， we reach to。A bar。Sibber， deeper。老。😔，Or B C， R D， or。A班D吧。Okay， then we need to。

 we can also cancel these two terms and we reach to sea bar。Debar。Plus。Or。B super d。And we can。

F out CBbar。This is Dbar or。B and d。Which then we can also simplify this too。D bar or B。



![](img/a353d04db1d832c56a5c2639e9019930_4.png)

Yeah， I got a message on my screen saying that it's live。

mCan anyone check the YouTube channel to see if theres or should I just go ahead？Okay。

 hello everyone， welcome to the problem solving session4。In this session。

 we will solve exam questions from spring 2020。And we'll start with the second question。

 a very long question。And yeah， I'll just get started with it。

So I hope you can see everything fine here and。Second question， Mari of question starts with。

Does the following code result in a sequential circuit or a combinational circuit？

Please explain your answer。And yeah， you when you look at this code。

 the first things you probably notice as the input of four bits。

Data input and output register name segments。And it's  seven bits large and then the always statement。

We have a sensitivity list of star， which means it will be executed when any of the data that's being。

Red and the essentially red in the always block。Changes and here there's a case statement inside the case statement when we're looking at the data value。

And for only five of these values。We have an assignment here for the segment output。

And because of this， because not all the left， sorry。Because we have segments。

As a left hand side up in these statements。And they are not assigned to evaluating all cases。

This is a sequential circuit。The answer is sequential。

And the reason why that I'm gonna explain a bit more。 So data is4 bits large， but。

And the case statement， they're only covering five。

Of the available 16 different values because data is 16。

 the data can have 16 values because it's for。Now because we don't have an assignment for other values of data here。

What this will output as a circuit is。Some circuit that's going to hold a state for the segment's output。

 so basically when the data is 4 d5 like basically data encodes the value five。This statement won't。

Reassign the value of segments so it needs to remember it that's why it will essentially generate。

 end up generating probably a latch in your circuit。嗯。Any questions about this one。Okay。okay，咁。

Moving to the next one， then。Oh。嗯，Yeah。Thank you。Yeah， zoom a bit and you can still see it that。ok。

And the second question is， does the following code result in an output signal which is zero。

 except for one clock cycle and every three clock cycles。😊，And if not。

 please enable this functionality by adding minimal changes and explain your answer。

So the module called divide by three and has three inputs。

 clock reset and sorry two inputs and one output Q and the question is asking if this Q is zero。

Except for one clock cycle in every three clock cycles。So we can look at this line。

 and this is where Q is assigned to its value。And Q will be set。

Essentially to one if this statement is true， right？Because we have this equality operator here。

明 I can zoo in a bit。ok。So whenever current value is S 0， which is。Here， it's it's basically zero。

Q will be  one and these as0 S1 and S2， as you can see， the encodings for the state machine。

 most likely。And the way they declared。And in the always statement。

 which is triggered on every input， like it's an always at start。statement。

So it's like where we define our combinational circuit， right？

The we look at the current value and depending on its。It's value， we set the next value to either S1。

 S2 or S0 here。And the default cases is zero， but it's not really important because we covered all the cases for。

Current value， but it's because it's2 bits we have to cover。

Another value which is not encoded here as S3 for example。

 so this is just doing that to make sure that this indeed generates a combinational circuit。

 there's nothing wrong here。But the problem is you can see that then the current values as0E assigned to like the Q becomes one。

But current value is。Only declareds here and there's no assignments to it。

So this is supposed to be a。State register， but the code that will make it a state register is missing。

And to do that。We need to add two lines of code， basically。

And we need to add a new always block to make sure that the data is registered。

The next value is registered to the current value and we want it。So maybe three lines。 Okay。

 so this is an always at。Poage clock。We want this to be triggered with the positive edge of the clock。

And a reset signal because。When the circuit is reset。We want the current value to have a valid value。

And then inside here， we will have if。Is it is tight。We're gonna assign。0 to the current value。

And if it's not。A they're going to assign。The next value to current value。

And what this does is it makes it a proper state machine。And then if you trace the code。

 you will see that it will the current value starts with zero， so it will output the1。

And we reset the circuit basically， and we set the reset signal and deposit and the clock hits。

The current value will be zero， so Q will be one in the next cycle。And then。The next value。

Willll be assigned to S1， S1 encodes1。So the current value。When the clock hits。

 will become one and then it will become two。And in these two cycles。

 it will output zero because this statement will。End up being0。

And then it will go back to state zero and when it comes back to state zero。

 it will output one again and it will continue forever。Okay， yeah， any questions about this， yes。没此。

对以。嗯，哎。Yeah， I think you can do it for this question as long as you said it to。Yeah。

 you can set it to anything because basically if you set it to。

 I was going to say if you set it to S3， then。It might not work。

 but this default case here will cover that。So next value will be zero in that case。

And then the current value will become zero in the next cycle。

 and if you set it to anything that's already listed here。

 then it's just going to continue the way it's supposed to according to the state。Yeah。生きて。是。

Think that would be correct， also。Yeah。嗯。Yeah， it will be trigger the block will the trigger whenever the reset signal changes。

 I don't think it's going to change the behavior for this question basically for this code。嗯。对的。不起。嗯。

Yeah， but then you have this if reset that prevents it from， you， executing。Okay。

If there's nothing else。Moving to the next one。真是。死。Zoom out a bit again。Okay。So again。

 we're looking at the where code this code implements a circuit and we initialize all inputs and registers of the circuit to0 ands what is already being done。

嗯。In the code， and we apply the following changes to the input signals in two steps。

What are the values of out and temp this register after each step？And then step one。Okay。

 maybe before I talk about the steps I talk about what the code is doing。So it has。

This time it has four inputs， one bit inputs， select ABC and out one bit output out。

And inside the module we define register， that's assigned to zero。

And we have an always block here that's triggered when the select signal or cell signal is and it switches value。

So there is like an if statement here an else statement that complements it。I think this。

There is like a problem in this code。 So there should be begin and end statements here。Basically。

 to make sure that those two lines of code remain in the。

Correct place like in the if statement and in the al statement。Yeah， and then。嗯。

In these if and L statements， we have assignments to temp and out。嗯。So in step one。

 select signal will change change to one。So what will happen is this always block will be triggered because cell changes this value from0 to 1。

 it was0 in the beginning because the question says we initialized all inputs and registers of the circuit to zero。

Now we change it to one and they always block both again get triggered， as I said。

 and then the block that will be executed as the if block。What happens is。Tempamp gets assigned to。你。

A and B， A A And B is not。Or like the inward value of A and B。

And that's going to be because A and B are0， this is going to be one。So， in step  one。Tempamp， well。

 one side。 Well， yeah， T will be one。嗯。Okay， and the out is the x sort of temp。And see。

But because these are non blocking assignments。The value of the new value of temp。

 which is one is visible only at the end of this always block。

So this line of code will still or this statement will still operate on the earlier value of 10 which is zero。

嗯。Is that correct， yeah， because temp is in the beginning zero。It will operate on the。

On that value of1， which is 0， and then it will exhorpt that with C， which is also0 and0 x or 0 is。0。

 so out for be0。No。Let me double check if there's something wrong。😔。

It's one bit and it's going to be you。Yeah， I don't think we're missing anything so in step two。

 while select signal is still one， we change B to 1 from zero to1。

This won't do anything because if you check the。Sensitivity list of this always block， it's on south。

So this block will be executed only when the cell signal changes value。So when B changes。

 it's like when the value of B changes， nothing will change。

The block won to execute basically and then because the block doesn't execute none of the values here change。

And that's the。That's the solution basically in step two。嗯。The always block is not executed。

 so tempmp is still one。And all still。0。Do you have any questions about this one？Okay。

 then it's the finals。Question for this problem。There's another code。

And it's asking if the code is syntactically correct and will result in deterministic values for all signals。

And if not， please explain。So this module has two， two bit inputs and one。Okay， in one is 2 bits。

 but in two is。Also do it。 yeah， I guess。Anyways， it's not going to be important in the end for this question。

And there's an input called op and output，2 bit output register Z and S is a1 bit output register。

And there's a wire declaration here named T TMP。And then we have an always statement that makes an assignment to this Tmp as in 10 and in 20。

So this is the first mistake。The problem here is because this TMP is declared as a wire and we're making an assignment to it in an always block。

 so that's not correct。Basically， this should either so this is incorrect problem one。

And to solve this， we can either make。Well。甜屁。Definition。Or the will be registered。

Or we somehow remove this assignment from the always block and make it a。

Assignment and outside the old baseball。By using a sign statement， for example。

The next line we have an assignment to Z， and then it's TMP and OP。This looks fine。

 there's nothing wrong with this line。And then。The second always block we have another assignment to1。

 so this is another problem。嗯。Because we already have an assignment to TMP and the first always block。

The second always block has the same sensitivity list and it's。As making an assignment to the same。

Well， well， because TmpP is wire this is wrong to begin with， but if even if TmpP was a registered。

This will be wrong。And I think the easy way to think about it is when you have two always blocks。

 you don't know when they will execute in the real sense， so you have two combinational circuits。

Driving the same signal。But those circuits can be different and how do you connect two output wires of two circuits to a single wire without using any gates and stuff and this is the problem here basically so。

I think this is called multiple drivers issue。So， I will just。Type right that way。

 so there are multiple drivers。off。天 p。So this should not happen。And this is the second problem。

 the final in this line， we don't have a problem here because Z is registered here。

 defined as a register and we're making an assignment to it in an always block， yes。对。I think so。

 I think this is a， this should be O P yeah。Yeah， but I mean。

 if you notice this and like in the exam said that P doesn't exist， probably。Yeah in the solution。

 we don't have that， so I'm assuming this is a mistake。But you're right。

 P is not declared well for at least in very log， well in Vivada， what happens is I think it will。

If it。The compiler cannot find the definition of a variable if will'll just put a zero over there。

But。Either way， it's fine， I think。Yeah， and finally we have this assign statement here。

 were making an assignment to s， but s is defined as a register and this is the third problem。

So we can use assign statements outside the always blocks to make assignments to registers。

So this should have been defined as a wire。And to fix this， we can change the。Definition of S。

Should be wise。Or we move this inside an always block if you want to have the same behavior。

Any questions here？Okay， if not， we're done with this problem。And we can move on to the next one。毕。

Yeah。Any question？ok。保证。Yeah。嗯。So the next question is about finite state machines。😔，Okay。So first。

 it says that you're going to need a more finite state machine。

 so you have to draw the circuit accordingly， not the circuit， but the machine accordingly。😔。

And it's going to detect。A beat pattern， which is 0，1，1。On like swimming input from eggs。

And when it detects a 011 pattern， it the1 bit output y is going to be 1。

So this is like you have some patterns and then you're going to have  one0， then 1，1 then 1，1。

 and then the remaining doesn't matter， but at this time the output y should be 1。

And how you start is the initial bit value of x is0。 so in your first reset state， which is a0。

 you assume that you have x equals to 0， so you have a pattern that is like some sum pattern and ends with0。

And since you did not observe 11， the last bit is 0， your y should be equal to0。

 And since this is a more finite state machine， your output only depends on the。

On this state you are in then if you have， for example， another zero。

 then still your last bit is zero so if x is equal to zero you stay in the same state。

But if your x equals to one， then you go to another。State， which is。W which is a pattern。

 which is I mean， just describes a pattern that like the initials one are not important。

 but it ends with01。So in this one， if you got any0， then your pattern becomes something something0。

 so you have to go to this initial state where the last bit is0 but the last bit you observe is0 and in this one the output is also0 again because you didn't observe 011 yet。

And。If you observe one in this states。Then you will see at the pattern and then you need to go to another state which says。

 okay， this is x equals to1 and in this state you observed a pattern。

 but this pattern ended with 011。So this pattern， the output should be one because you absorb your pattern。

And if you observe a0。In this state， you have to go to this zero again because this is a state where you have a pattern that ends with zero only。

 but if you observe a one， you have to go to another state。Which is。

Which is a state where you did not very absorb a pattern that ends with zero directly。

 so it's not like you did not observe your target pattern any bit of your target pattern yet and if you observe one in this state。

You have nothing new in your pattern。 So you stay in your pattern， So you stay in your state。

 but if you observe a zero in this state。You actually go to the initial state。

 which is x equal to0 because you observed。A bit pattern that timess with0 and this state then calls this one。

 the last thing remaining is what is going to be the output in this state and this should be0 because you did not observe。

嗯。The big pattern you target yet in this in this state。 So do you have any questions about this。😔。

St machine diagram， yep。行都。所以什。You to go wherever。Yeah but in this one it says just assume that you have a zero initially so you you don't like search for the first zero because it's already given when you start your finite state machine that's why we start in S0 and then we search for one direct instead of searching for0 otherwise we would start in this S3 set and we would search for zero first。

But this。And in reset。新的。嗯哼。在人。Yeah， one。 That's why we start here with reset。

 and then we we search for one。But in this one， when we reach the pattern first。

 we go to this one again if there is zero， but let's say we start with one from here we search for0。

And then go to this one yet。 but like the this question just says initial be value of x zero。

 it could be one as well。 there's no specific reason why it's zero。 but if it's zero。Well， yeah。

 it could be nothing， yes and。Yeah， and like what I would do if I were， if nothing is specified。

 you can just say I assume this if if it's not clearly stated in the in the question。

 you can just say I assume this and I draw the state machine according to that。

 if nothing is specified already。Any other question？K。

So the next part of the question is about simplifying an finite state machine that is given to you。

But the first small question is the type of the finite state machine。

 is this a milli or more machine？So the difference between these two finite state missions is that if the output depends on the state you are in or the output depends on the state you are in and the input that you have and in this state machine diagram if you can see the outputs are here and the inputs are here so the output depends both on from which state you are traveling to which state and then the input。

So， for example， if you are in this state， the input is one， you get zero。

 and this is not a good example if you are in。This state， for example， if your input is zero。

 your output is zero as well， but if your input is one。

 your output is one so it depends on the input as well， then this is why this is a merely machine。

And the next question is about whether you can simplify this state diagram such that you reduce the number of states。

And if you can do that， the question asks you to draw a finite state mission with the minimum number of states。

So what you can do is to first maybe try to understand what this finite state machine is doing。

 but even before you can see that this state is never reached because you stay in this S2。

 you start with this S2 and then there's no edge that's going to S0 so you can just maybe even delete this part of the FSM。

And for the remaining three states， we know that S2 should be here for sure because this is a reset state。

And then you start with S2 with three sets。And if it's 0， you stay here at 0，0。Okay。

Or what about S1 and S3， are there any redundancies here， maybe we can check。So if it's zero。

 we stay here， but if it's one， we go to one with the output one， but if we get another one。

 we go to this state， which is zero。And like S1 and S3 behave similarly when they receive zero both go to S2 state with output 1。

So we can maybe just think that。They behave similarly because if they receive a one for the first time they output one。

 but the other ones they just stay for example S3 stays here and then output zero so and then this one goes to here and then S3 stays like like in the remaining ones you stay here so maybe we can just remove the redundance in S1 by removing this and then converting this arrow from here to here and then we do one1 here because for the next ones and then the zeros S1 and S3 behave identically。

So we can have it as 1，1，2， a 3。And then we stay here if it's one。

 and then we go to the initial state， if the。inputput is。Zero and then this is going to be the sorry。

 the simplified state diagram for the sorry it could keep the machine given above。

Do you have any questions about how I simplified it。And okay。

 so there' is this one last question which is like the purpose of this machine。

And for what purpose can it be useful so we can first check maybe what it's doing。

 what what kind of input is' capturing。We see that we start with a diagram and if it's zero。

 we just stay there， but if we have a pattern that's 00 so and then we have one。

 we have an output here and then if we have remaining ones。

 we don't have any output like you have output zero I mean and then if you have any zeros then you can have output one and this pattern goes like this so you have outputs when your input transitions from zero to1 or one to zero。

So， it's kind of。Like detect ages from 0，1 to 10。Yep， that's kind of all do you have any。嗯，跟 you系 me。

Yeah， so let's look at fourth question。It's a relatively simpler question to answer with。

Two options for every question。 So the question goes like this。

 So it test the understanding of IA instructions that architecture and micro architecture。

So a new CPUU has two comprehensive user manuals。Available for purchase as shown in table one。

 so you have the Ia dot PDFdf and the microitecture dot PDFdf。买一些诶。The manual costs 1 million francs。

 and it gives the D IA in detail and the micro architecture manual gives。

Details on the micro architectureitect， and it costs 10 million。s。

 so unfortunately the manuals are extremely expensive and you can only afford one or one of the two if both manuals might be useful。

 you would prefer the cheaper one。So for each of the following questions you would like to answer。

 decide which manual is more likely to help。So for this question， if there is an incorrect answer。

 well subtract one point and if there is no answer for some of the questions， well lower zero points。

So， let's look at。A very simple diagram of where ISA sits。

I SA is like an interface between the the programmer and the hardware or the micro architecture。

 So here you have。And it gives a kind of a model for the programmer。

To understand the process and and its workings so。Languages like assembly or higher level languages will use the instructions with architecture to basically do the program。

And。睡后。😔，plus。So let's look at each of these questions。

So the Nteger multiplication algorithm used by the AU so this is something which is very。

 very specific to the the AU or the micro architectureitecture and this is this is not exposed to the programmer so。

So the answer for this is。micchael architecture。And the second question is the program counterwith。

So here， this is something which。Wwhich will be specified in both the IA and the microarchitecture。

 so basically the program counter will tell us what is the next instruction that gets executed or the address of the next instruction so so the width is also specified in the ISA and that typically tells us the the width of the address bus so and that is required by the programmer to。

Basically， I understand the current instruction that is being executed and things like that。

And so for this is the IS。Next question is branch mis predictiondiction penalty。

 So branch prediction is。Is typically transparent to the the programmer。But I mean。

 sometimes the compiler can give hints to the for successful branch prediction。

 but the penalty is something which the programmer will not know and the penalty is usually calculated by the number of cycles which。

Which which were wasted by the mis prediction。 So this again， is。

The micro specified in the micro architecture。Again， the second question you since。

It could be specified in both the manuals， we still go with the IA because its the cheaper one and the ability to flush the TLB from the OS。

So TLB flush is is something that is triggered by the kernel or the operating system。

 so when there is when the software page tables are updated and the TLB has to be flushed because it has stale information so the the OS will use some registers provided by the which are mentioned in the Ia to trigger the TLB flush so this would be。

对。嗯。This can be found in ISA and the size of the reorder buffer in the out in an auto of order CPU So again。

The reorder buffer is something which which is still which is again transparent into the programmer and it is specific to the micro architectureitecture。

 so size of the reorder buffer is something which the programmer wouldn't know so the IA does not mention that。

Anyway。So it， it's still， it's in the micro architectureitecture dot P Df。Any questions for。

So the fetch width of a superscalear CPU。 So in a superscalear CPU。

 you you can handle multiple instructions in a single cycle in the pipeline。

 So the fetch width is again something which。The the ISA does not provide because it's not something that the programmer can have any control on。

So啊。So， this is。Specific to the micro architecture。 and it's in the。

In that manual and seem the instruction support。So it simply is basically single instruction which operates on multiple data elements。

 so this is the basis for vector processinging and。SMly needs support in both hardware and software。

So if you would find mention of Cindy in both IA and the micro architectureitecture PDF。

If you want to look at whether whether the C is supported， it would be available in isa。pdf。

If there is support。And the memory address， the next question is the memory addresses of the memory map devices of the CPU。

Example keyboard。 So if， if a programmer has to。Rightide drivers for the keyboard or mouse。

 which is basically memory map devices。The programmer has to know the memory address the of these devices。

 so that would be something which would be pre available in the Ia dot PDFdf。

And the number of non programmable registers in the CPU。

So you have both programmable registers and non programmable registers。

 so programmable registers are typically mentioned in the ISA。

 but then non programgrammable registers are something which the micro architectureitecture or the CPU uses for its internal purposes so that would not find mentioned that is not mentioned in the ISA and it would be available only in the micro architectureitecture。

嗯 any questions so far。So the the next question is the replacement policy of the L1 data cache。

So the。Multi level caches are are transparent to the to the to the programmer or。

At the high to the higher level abstractstruction so it is it's not so the ISA wouldn't actually provide any information on the on the L1 data cache or the replacement policy of that。

You would typically find mention of the the cache sizes。

 but the replacement policy is something which would not be available in the ISA and that would be there in the micro architectureiture you can only find it in the micro architectureitecture menu。

没。Sure，没关。嗯。The next question is the memory controllers scheduling algorithm。Again， this is。

This is something internal to the micro architectureiture and would not be the would not be exposed to the IA or the programmer。

 so this is。This is available in the micro architectureure PDFf。

The next question is the number of bits required for the destination register of a load instruction。

So typically in the instruction set， you would find the width of the source and the destination registers for all the instructions。

 so that should be available in the Ia PDF。And the next one is pretty easy。

 so description of support for division and multiplication between registers。

 so if if there is support for these two operations， it would be available in the ISA。And yeah。

 then 14th question is the mechanism to enter in a system call in the voice so system。

When an application wants to call。Once to enter a system call。

 it has to typically execute a software interrupt or something called the trap instruction。

 which should be mentioned in the ISA manual。So， that's。我跟 the。The IA dot Pf。

 so any T rule is anything which which is performed by the OS or the application is something that needs to be mentioned in the IA。

And the last question is the size of addressable memory so this is something which the application the programmer should know when when allocating memory for the applications or when when basically to know the the virtual memory and the physical memory sizes。

 so that should also be。Available in the I A ort P。吔岁。嗯 any questions。

So I'm going to solve the performance evaluation question once again。And。

I guess the best tip that I can give you to a performance evaluation question is read the question really carefully because often the answer is quite simple。

 So just let's just read it。 So cycleprocesor P1 is acute load instructions in1 cycles is store instructions in eight cycles arithme instructions in four cycles and branch instructions in four cycles consider application A where。

20% of all instructions are load instructions， 20% of all instructions are store instructions。

5if% of all instructions are arithmetic instructions and 10% of all instructions are branch instructions。

And so the question is starts， what is the CP of application a when it's aing on processor P1 show your work so basically to calculate the every CPI you basically multiply the number of cycles that is going to take for a type of operation to the amount of instruction that the application is going to is acute so because this is cycle for instructions right so the CP here。

Is going to be low destruction takes ten cycles。Times the number of load destructions that you have or the breakdown。

 which is 20%， so times 02。Loose。😔，Story instruction takes eight cycles。

Time is how much storage instructions you have，20%，2。2。Ourit construction takes four cycles。

Times the amount of ultimate construction that you have，50%。老s嗯。You have four cycles。

For brain destructions and the latency of the amount of branch that you have 10%。

And I'm not going to make the map。 I'm going to look at here。 So it's going to give6。

Really important， I think I said this last time in the exam more important that get this six correct like the number six more important than this is to have the equation correct so if even though if you make some mistake when you're doing the math if you leave the equation。

Clear enough so the TA can understand what you were thinking when you were creating the solution。

 you're not going to be deducted so many。0 for math mistakes。So any question related to this？Okay。

 good。So， park B now。A new design of the processor doubles the clock frequency of P1。

 however the latency of the load storage met can brain instructions increases by two，2。

2 and one cycle respectively， so we call this new processor P2 the compiler used to generate instructions for P2 is the same as P1。

This is all of this is going to be relevant in the next question does it produce the same number of instructions for program a what is the CP of application a when executing processor C to show your work so it's pretty much。

C p i。😔，Be true。 Let me put here。 be one。retty much the same that we did。

 but you are going to include those latencies here on the CPI calculation so。

Since we say in the question that the compiler is the same。

 the breakdown of instructions is going to be exactly the same so you can keep this。

 the only thing that you need to do is add the number of latencies， the added latencies。

 so we have the original 10 cycles for low destructions plus you're adding two cycles for low destruction so plus two times the amount of low destruction that is executed。

0。2。Plus， original latency for store instructions are A is8。

 plus you also add two to store instructions。Times the 20% of load structure that are executed。Blows。

Original latest software arithtic instructions plus how many cycles was add to。Times the 0。5。Plus。

 original latency of branch instructions for。Plus one cycle that was added to branches and the amount of branches that are executed。

And this is equal to 7。9。any question。Okay， maybe not。So then he asks which processor is faster。

 P1 or P2 and by how much and sure your work。Again， the most important I said this last time also。

 really important equation to remember is the equation time equation， so is execution time。

Is equals to the number of instructions。Times the CPI。Times1 over the clock。Frequence。

So we' are going to assemble both instructions for both processors， so execution。

Time of processor1 is going to be the number of instructions that is is acute。

Times the CPI that we calculate in the previous question or six。Times1 over its frequency。And。

And the execution time。Or P2 is going to be the number of instructions。

Times the CP calculating the previous question，7。9。Times from the other question。

 we saw that the new design doubles the clock frequency， right， So if the frequency was1 over f。

 this is going to be over2 f， right。嗯。So now you basically need to calculate to inequality to see which processor is faster。

 so for example， we can assume that。诶。P2 is faster than P1。 So if you assume the execution time。Or嗯。

Itu is smaller the execution time。It of1。This means that。The execution。Time of B 2。

Divided by deecution time of p1 smaller than 1， then you just verify the in equalities 2 or not。So。

You can put the values here。 is the is going to be。Number of instructions times。

6 times 1 over F divided by number of instructions。Times 7。9 times 1 over2 F。 and you can simplify。

The equation， then I'm going to again check the solution because I don't want to do the math。

 and this is going to give 1。52 so。This means that。Be2 is faster。Then。Be1 by1。52 times。Okay。

 is there any question here？O good。So the last part of the question。Heres one。没有。Hopefully。

 you can see it。So there is some extra area in the chip of processor P1。Where extra hardware can fit。

 you can decide to include in your processor， a feather branch execution unit or。

A faster memory device。The Fe branch execution unit reduces the latency of branch instructions by a factor of four。

And the memory device reduces the latency of memory operation by a factor of two which design do you choose you can use the same equation here again of this equation time and calculate for the branch and for the memory device again。

 but is more cumbersome that is the adoms law that we learn。In I think it was lecture 20。

 So we have this formula here， one over one minus。The portion that your optimize。B。The portion。

That you optimize divided by the speed up of that。Speed up。Or the optimization that you provide so。

Let's apply this equation for both branches and memory units， so let's see they speed up。

Of having a faster brain unit。This is going to be one over。

1 minus the portion that you are optimizing right If you look back at the equation of the the question。

 10% of all of the operations are branch destruction。

 so you are going to being optimizing if you choose the branch only 10% of the total execution so it's going to be 0。

1 because this is a normalized。Plus， the portion that's optimize 0。

1 divided by by how much you' are optimizing that portion。

 so you're optimizing branch units by or destructions by four times so this is divide by4 if you do the math I'm going to check here。

 this is 1。08。Then you do the same for the memory。1 over one minus the portion that you are optimizing。

 right？This is a memory unit right so this memory units support both loads and storage operations so you have。

20% of all of the instructions are allowed and 20% of all of the instructions are stores right。

 so this is 0。2 plus 0。2。This is for the loads。This is for these stores。

Plus portion that you are optimizing 0。2 plus 0。2 divided by how much you're optimizing that portion factor of2。

And this is equals to。Sorry。Let me see here，1。25。So you pick the one that gives you the high speed up。

 right， So you pick the shoes。你。Memory unit。Oh it's a musician。So it's basically this。

 is there any question？嗯。CP。Yes， I was just want to show something different to do。

 so if you look at the equation， the solution here。

 I give the solution for using Ab law as I just did and that is the alternative solution here which basically rec CPI as we did in Perian A and B in the equation the equation that might be more straightforward but requires more math I guess。

So if you remember the a law from the top of your mind， which is extremely important。

 is going to be much faster。

![](img/a353d04db1d832c56a5c2639e9019930_6.png)

![](img/a353d04db1d832c56a5c2639e9019930_7.png)

Hey， does this work yeah。So we're doing the pipeline reverse engineering question。

So we get a pseudo coat。嗯， to the code assembly code。

And we should answer various questions about how this processor probably looks based on the cycle numbers we get。

And then， afterwards， too yeah。Should also count。How many cycles the program executes this kind of thing？

So。Let's see。 let's look at the code first so。你。First， load to registers。

Are one and are two with immediate。And then， we know that。P these。It used in。

to increment the counter， there is some kind of multiplication going on。

 some kind of loop bounce check。 And if the loop is taken， it jumps back to L1。So。

First question you should answer is list the necessary data forwardings between pipeing stages to exhibit this behavior。

So this behavior here means the behavior within the execution timeline。Specifically。

 the stalls we are seeing。So we need some specific data for writinging paths to cause。

Exactly these cycles of stalls。So， let's see。Whereread the data goes。 So we have a stall。

For dynamic instruction number three。And were cycles five and six stall。

And that is the execute stage， somehow awaiting the input values are 1 under2。AndSo， specifically。

 the。Are two value。From the second dynamic instruction。From the execute stage3。😔，To here。

 we are awaiting this value。 So that's one path we're getting。

 And we're getting at least also the R1 from here to here。And we know that at least at this point。

 the value must have been ready because execute of a starts here already。If we didn't have the value。

 the execute stage of the addition couldn't start。Okay， so we know that。

And then we have some more stalls to look at。we have also a。In cycle nine。

And you can see in cycle9 is we are awaiting。The R one value from the addition up here。

So let's see this is the result from this execution is available。To start execution one here。

So and what we see both times is that。At least， there must be。嗯。Awarding。From。E328 one。Let's leave。

Yeah， that has to be at least there， so we are not stall longer here。

And the second thing we're seeing in the remaining stall。Is that。The jump condition。So jump 0。

 actually jump， not 0。Yeah， I guess there's still an issue shouldn't you。

Question here this should be jumpnu 0。So this。This jump condition is checked here in E1。

And it awaits the value from this subion。 So it jumps。If this subtraction is not zero。So。

 we also have。Some kind of forwarding pass there from E to Iran。 So we are also forwarding。嗯。Oh。

 thank you。Im sorry also。I' me check。Yeah， we're also forwarding the condition registers。对。So yeah。

 the reason we see this is that the execute stage one of。

Jump down0 starts the next cycle after we got the subtraction result。Okay， so that's question A。

 is there question to here？Great。All right， so does this machine use harder interlocking or software interlocking？

Well， so software interlocking would be。That there would be some kind of no ops in the assembly code。

Hard interlocking here means that the machine automatically detects that there are data dependencies and it automatically stalls until it can resolve these data dependencies。

 So there is。Hart。Where。就 looking。😔，Because of two reasons。There are。no。😔，nops。And the some code。嗯。

She installs tuf and necessary。😔，对。帮 two啊。😔，Question here。 so we should。We ask to rewrite these。

And the execution timeline， basically。嗯。So before we had we answered in B that we had hardware interlocking。

And now we should do the opposite， so we should do。Softer interlocking。嗯。

And we basically should rewrite this。Yeah， execution timeline accordingly。

 So what we need to do is we take。The instructions you had before。

We insert knobs in between as needed to account for these stalllls that would happen with forward vent locking。

And yeah， write down the cycle。啊。系咪。So let's see I'll start。

 I'll number my dynamic instruction0 based。So it makes a bit more sense in the next sub question。

 but you could also start with one here。Okay so first instruction is this movie immediate。

So this is edge decocode execute one。Exe2，3 memory right back。嗯。Second instructions move in R one。喂。

H one。To memory。 And we should continue the table down here。So it should be our too。O。

So third instruction is this addition， but there's a stall first so as you can see over here。

The addition， if you had harder interlocking the， the addition would later stall to eva the value from the move instruction。

And and。In software intering， we cannot make the machine stall automatically because it doesn't have the data already right。

 so we need to insert knobs。So that there are no stalls happening later。

So we need for to account for this two cycle stall here， basically， we need to insert。

2 cycle verbs on knobs。So let's right also。time here fetch the one。😔，wo three。Okay，No。

No idea why I started telephone phone。 this should be like this one。😔，2。😔，ok。嗯。Let's see。

 So we got our install accounted for。 We can continue with the ad instruction。C啊阿光。Wang。😔，2。😔，ok。😔。

Let's see。 So after the ads， the multiplication executes immediately there。

So the deplication also stalls， but only because the addition was stall first。

 we've already accounted for these with no ops， there's no additional stalls in de modification so。

There are nono here。😔，Okay， and now we have a。Stop。Instruction。

 let's see in the hard interlocking case， there was a stall here because we were waiting for the result from the addition。

So we cannot start with this sub directly here。 we should have anob again。Then we can have stop。

Allright。And finally， we have this jump instruction。

So this has two additional stalls on top of what subi already installeded because it's waiting for the result from this abstracttraction。

 so there's two morenobs needed here。So let me write them down here， maybe。And finally。

 we have an jump。我 should be jump not zero。😔，系啊，啱。O。So， let's this exercise。

Are there any questions here？嗯， good的。Yeah， as you can see the table is a bit boring。

 and the interesting part is probably where to insert the knobs exactly。Right。

 so we need and this result for the next sub exercisese。😔，So we get some additional information。

We know now that。日播放。And then I' have some information about what the branch looks like。

We are asked to calculate T。 So what the current clock cycle is if currently the value of R 1 is 98 and we are currently fetching。

The addition。 So let me show you the code again。So we know that these two both get initialized to one。

We know that the value that's currently stored in R 1 after some execution is 98。

And we know that you are currently fetching。This instruction here。The the ink。

 so this is really an increment。 If you initialize both these one， then this addition is really。

Or one plus equals  one。Okay， so。What this means is。嗯。Let me see。 I wrote this down very nicely。什么咧？

ok， so诶。We know the loop counter here， so really the code what the code ends up being is you have some kind of loop。

And you'll initialize some kind of loop counter or one to one。It's given up here。

 and you have some kind of increment that you initialize to one also。

 And then at the start of every iteration， you increment your loop counter。

You do some kind of calculation。Here you check。If your loop counter is exactly 100。

And if it is exactly 100， you stop the loop。嗯。And so you。

 you should write some kind of explanation here。I does。And what this should。Result at is that。

 if currently。诶。Currently， our one is 98。Then we have already executed。well。

 then our one has already been incremented。And97 times， right， It started out at one。

And it implemented 97 times。 Now it's at 98。And of the current iteration。

 because we are currently according to the exercise。

 we are currently fetching this increment of the current iteration。

 the increment hasn't happened yet。AndSo there have been 97 past iterations。And诶。We are currently。

At the start of the 98th iteration。ok。So far， so good。

Now we take this information and we have to calculate cycles。Fortunately。

 we already have to sta over here， which makes the cycle count much easier。

Although this machine uses hardware interlocking， we get the equivalent cycle counts with software interlocking so we can really easily check how many cycles。

Certain range of code takes。数。Let's see till the first iteration goes from dynamic instruction number0 to dynamic instruction number 10。

 because you have these two additional nationalization operations and knobs， so this is 11 cycles。

走 first。Turation。1even cycles。And then any further iterations， the jump would go。Right up here。

 right from So you go from here。Right here。And you don't need to redo the onops。

 There's no benefit to that。 You start with the addition immediately。And this is what12，3，4，5，6。

7 instructions。 So7 cycles so。啊。好。The next 96 its。Like7 cycles each。And then of the last iteration。

 since we are currently only fetching the first instruction of the last iteration。

 there have no cycles been spent in that iteration。So we just have to calculate。11 plus 96 times。

seven。😔，And there's。Yeah， so maths for you to do。 And I calculated thats。682。Okay。嗯。It could be。

 yeah， depending on how in number instructions here。 So I started with 0。

If you number instructions here from one， like it's done over here。

 then you might end up at 683 here。That doesn't really matter。

 It's good that you just write down whatever you assumed here。 If you count it 0 based or one based。

对。呀。😊，对。And the in the the the cycle。但是本来。Start right up the top here。

Even if you have a month to certain， it could take to one。这个。有是你呃这交。Yeah， it's a great question。

 So I'll repeat it have a recording quickly。 So the question was if。If you have this jump here。

This solution here assumes that there's no kind of delay or well stall wouldn't be accurate。

 but there's no delay between here and starting the additional instruction here。

 even though we need some time to probably even realize that this is a branch。And that's yeah。

 good point。 the master the solution that we have for this question kind of assumes that there is no such delayle。

 This is possible if you have。For example，A processor where in the fetch stage。

You can immediately check that it's a jump instruction and you can immediately get the jump target。

And then this could kind of work。 And then your branch predictor predicts always taken and you wouldn't get a stall。

so。It's probably good and unfortunately the master solution doesn't do this。

 but it's probably good to write here。By the way， this is assuming。

The branch target is available after the fetch stage。Then you don't get the installed and it alls up。

But you're entirely correct， if you assume。Something else， for example。

 that the branch target is available after Decode， maybe， which is maybe a bit more standard。嗯。

Then you would have at least one cycle， additional。I delay there。Yeah， it wouldn't be really stall。

 it will probably be the pipeline being flushed， but。Anyway， yes。

 that would add that would change the calculation a little bit if you write this assumption in your solution then that's entirely correct。

Is that good。😊，听咩咁诶。So his matter， I mean， you could have been completely like start。包开关的。

Thank you different。那你们是系都相。对是。I mean， we don't just look at your number and see。

 is that the number on the mass solution and what's more important than the final number is like how it derived this。

Hopefully， if you're off by one， then 90% of your derivation is correct。

AndSo there should be some points。Yeah。是。Alright， so finally， a bit of a easy question。

 we should calculate n。 So this is the dynamic instruction number。嗯。So what we really ask is。😔，嗯。

Given that we are in the 98th iteration。How many instructions have executed so far。

 we are fetching this one。The ha， yeah， what's the index of this。

 What's the dynamic instruction number of this。Instruction when youre fetching it in the 98th iteration。

That should be super simple。嗯。Yeah， question because you simply have these。诶 to。

Instructions there before the loop。plus。Let's see 97 iterations that you already completed of four instructions each。

And then well， the current one， depending if you're zero based or one based， if you're zero based。

 it's exactly this number， all devices will be plus one。And。We are also already calculated this。

That's 390。Yeah。And well， you should write a little bit of text there， write how you arrived at this。

哎 numbersumbers。But you go to this multiplication。So today I will discuss the Thomas So Gordon question。

Now this is an important question， so before we discuss this question。

 I would like to give you some examples。six months ago I wrote the same exam and I got a good score so I would really like you to do well。

 so the first tip that I would like to give you is like take a deep breath， just relax。

 try to understand the question okay， read the question first it would be surprised how many people make mistakes simply because they don't read the question。

Form a mental diagram of what you're going to do， form an image of the question in your head。

 and then try to solve it。All right， so I'll illustrate this process so you can get an idea of what I'm trying to say。

Now， this question says that we want to deal with Tommoil algorithm。

 we want to reverse engineer a processor's implementation for this Thomasmoul algorithm。

Let's start reading the question。Okay， so as I just said， read the question carefully。

We consider a scalar processor with in order fetch。

 out of order dispatch and in order retirement execution engine。All right so。You have。

I can write on this。Not not on this， right？对。All right， so。Yeah。

You can see clearly that we have a scalar processor， I hope you know the word scalar。

 it means simple， not not vector。Draw the processor。 drawaw the box。 Okay， you have an order fetch。

You have out of order dispatch。And you have in order retirement。Okay， good， we got the done。

 Now this processor has four main pipeline stages。 you have fetch。To code。

Execute and you have right back。Okay。Right。Just see that I'm just trying to understand the question。

 I'm not trying to solve it right now。The processor implements a single level data cache。 All right。

 this is our cache。Up next， the processor has following two types of execution units。It has。

It has an A U or and it has a memory unit， but we do not know how many of these units the processor has。

 All right， now， let's draw these on our diagram。 You have the A U right here。

And you have the memory unit right here now notice that I gave some space。

 I left this space because the question explicitly mentions we do not know how many of these units are there right so there is still scope to expand it in our mental image。

Perfect， so the AluU executes inteor instructions。It clearly specifies which instructions those would be addition。

 multiplication， move and branch， and the memory unit executes load and so instructions。Okay。

 this is known stuff。 This is nothing new。 We know this already。So AU would be all。Addd。

Multiply right and the memory unit would be this is the most important part load store instruction so always remember when you see Thomaslo load stores are going to be your problem be careful with the load stores and everything else will be okay okay。

Right， up next， we see the question says。The processor is connected to a main memory that a fixed actually All right。

 So let's say that this is the main memory and。All right， he got the main memory down here。Next。

 the question says， load store instructions spend cycles in the E stage exclusively for accessing the data cache and the main memory。

Right， so what does this statement mean， We saw that we have these pipeline execution stages。

 This question is saying that。If I do a load store， I will do a fetch， then I'll do a deco。

 then I'll do a execute， and then I'll do a write back but。If this data is not in the cache。

 then I will have to wait in the execute stage and this is your key right so I told you the question is very simple。

 you just need to read it carefully。This point clearly tells you that if there's going to be a load store that is going to miss in the cache。

 then this execute stage will be the one that is stuck okay。

 so we will see up next why this is a very important point。😡，ok。And finally。

 the question tells us there are two reservation stations， one for each execution unit type。

Let's draw the reservation stations。This is the execution unit， ALU and memory。

 and this is the reservation station。The reservation station reserves the instructions before they schedule for execution。

 okay？The reservation stations are all initially empty。

The processor executes an arbitrary program all right so arbitrary might sound confusing or difficult。

 but always remember the question is meant to be solved okay。

This question does not have anything that is not known to you， it is designed to be solved。

 so if you just read it carefully and do not get thrown back by these kind of words， you will do it。

So from the beginning of the program until the program execution finishes seven dynamic instructions enter the process pipeline。

 notice the word dynamic that is your hint that these instructions might be scheduled differently you know dynamic could be anything it could be waiting because of loads。

 it could be branch prediction it could be Thomasmo solo so yeah I'm just trying to build up the environment of how you should think in order to get this right。

Now table three shows the seven instructions and their execution diagram All right。

 this is perfect so。The question has given us the exact execution diagram for how these instructions will be scheduled。

Up next， we see the instruction semantics， which tells us， okay。

 what the instruction means and what it does。We can we can let's let's keep this at the back of our head and right now focus on this very interesting new data point that we've got that would be the table three as we look into table three we will come back to the instruction semantics to understand what each instruction does。

Now in table three， I start reading table three and I see that the first instruction is a move instruction。

Remember our diagram I told you to be careful about load stores。

 so whenever you see a load and store instruction be careful about that right now I see a move instruction which I know is not a load store so okay this this should be easy。

All right， so I see a does a fetch， it is a Dcode， then it does execute with four stages and then it does it right back Okay。

 sounds good I know this。Up next I see a load all right now your buzzers should be ringing or something it says load r1 r0 so it loads a value at address r0 into r1 and now I see it does a fetch it does a decode and then it stalls okay why does it stall it stalls because I see even e to e3 e4 arguing going it its it's used in the just previous in the previous instruction all right。

Up next， I see that it executes eight cycles in the east stage。

This question gave us a very important data point。If you remember， it said clearly that the。嗯嗯嗯。Yes。

 load store instructions I hope you can see this load store instructions spend cycles in the e stage exclusively for accessing the data cache okay we should connect this point at this stage to this instruction and see that okay this is eight instructions that are eight cycles。

 not instructions that are being spent in this stage waiting for the cache that means this is a memory access and we don't know if it was a hit or a miss。

But yeah， I'm trying to get you to float to the question， see what the data is given to you。

 because at the end of the day， remember that it is meant to be solved， do not be thrown off by it。

All right up next we have branch if less than r1 al right and I see that does fetch decode it is waiting until this execution stage gets freed and then it does even E to e through e4 that sounds good I mean that means that I could not schedule it immediately but yeah there was no waitinging or there was no low stores in this perfect。

Up next， I see this very interesting data point called squashed， okay。

Bringing you back to the instructions that were given the question， remember this word dynamic？

And you see dynamic think of memory or think of branch predictors， okay？Like。

It usually almost always means memory or branch predictors。😡，Now we see that this was squashed。

 squashed means this instruction was getting executed， but in the middle the processor said no。

 this result does not matter， I'm not going to care about it， I will kill this right away。😡。

So it's called in flight termination of the instruction。

 you see that both of these instructions were squash。

 that means there was most likely a branch predictor or a cache access at this point now do we see a load instruction before this。

No。We see a branch instruction before this， right， That means most likely， this was a branch miss。

And。These instructions were squashed because we took the wrong branch that we were not supposed to take and now we should correct our path。

And that means we take take the next instruction that was executed correctly after these now what does correct execution mean correct execution means this instruction was executed to completion。

😊，Completion is very important this w you see this w means right back。

 it means the instruction was completed， it was not killed in between。I hope that's very clear。

Putting it all together， what we see has happening here is that。

This branch as an instruction has now jumped to this one， okay， and these two。😡，They got killed。ok。😊。

Now， I can understand that at the first loop， it might seem complex， but yeah。

 just just hold on and we'll come back and you'll see how it all makes sense。Finally。

 we have another store instruction coming back to the very important point that we saw load store instructions。

 spend cycles in the east stage exclusively for accessing the data cache or the main memory so now we see that this store instruction is accessing our memory value it's accessing r0 and if you remember in the first instruction this was also accessing r0 and we did not update r0 at any point。

So this means that this is also accessing the same memorylocation and another very beautiful point here that you can see this E1 is it takes just a single single cycle so this instruction spends a single cycle in the execute stage compared to this one this load instruction which spent eight cycle in the execute stage do you notice the difference can you guess what where does difference come from most likely a cache miss yeah you're absolutely right。

All right， so yeah， we have set up the premise of the question。I can take questions after words。

 I would like to complete this on time。Okay good so yeah we have just read the question i've not solved anything so far remember the trick is that you have to read the question first carefully right now all I have done is created a mental image for this question right you have unlimited supply of paper in the exam use that paper to create this mental image。

😡，Do not try this all but like ha haaz。😡，Okay， now let's take a look at the questions and then we'll try to fill in the gaps in this mental image that we have。

So， the first question that we have is， what is the cash hit latency？嗯。😊，If I say cash hit latency。

 immediately， your mind should come to， oh， cash would be somewhere on the load store path， right？

 And we saw that we have。Los of instructions for the same address which had different access latencies right remember we clearly identified that okay。

 there was one instruction accessing the same memory address another instruction accessing the same memory address。

 but this one took eight cycles。Sorry this one took one cycle okay so that means that one of these instructions hit the cache and the time that it took to access the cache is the cash access latency you see it it's right in front of you the answer is always in front of you you have to learn how to find it that's the trick。

Okay， I'm not going to solve it right now， I'm going to keep reading。

 I'm going to keep filling in the gaps in my mental image。😡，What is the cash mislatency？Okay， yeah。

 so I was reading this question， what is the cash mislatency？

This is quite similar I just saw it right so if if my cache hit latency was one cycle that I just saw then the other one must be the cache miss because that is what was loading the data in the cache so that that should be eight cycles as we saw in table in this execution diagram。

This was a cashsh miss。And this was a cash hit。All right。What is the cache line size。

 the third question is what is the cache line size h interesting。Now， when you see cache line size。

 you should think about how do I figure out the cacheline size。

 I can figure out the cacheline size by changing the address that I am accessing。But。Surprisingly。

 in the entire execution diagram that we saw。We never change the address。 So if you look clearly。

 you can see the stores and the loads happen all at R0 and the value of r0 is let me let me zoom in。

Right。If you look carefully。R0 value is what is being accessed in the memory and r0 never changes。😡。

O， so。I don't know yet， I would need to read the question once again to figure out what is the cache line size。

Okay， well， that means my mental image is incomplete。All right， let's keep going。

What is the number of entries in each reservation station？So。

Do you remember the reservation stations that we saw？Yes。

 so these reservation stations are used to store the instruction before they are scheduled for execution on the ALU or the memory。

What is the size of this reservation station， the size of this reservation station is the amount of instructions that are executing concurrently。

 what do I mean by concurrently？First of all， first of all。

I hope you understand Thomas Solo and you understand how we schedule on ALU and we schedule on memory if you are not clear on that。

 I would be happy to explain it separately after we do the question。But yeah。

 you have to think about the size of the reservation station。

 you have to understand how many instructions are in flight or in execution at the same time。

In the execution diagram that I see， I see these two instructions。

 for instance I see this branch and I see this mu now I know that branch and mul will both access the ALU if you remember we were clearly indicated that they act as the branch and mu and both of them I see them concurrently being executed right so that gives me a hint that maybe they were both executed at the same time and yeah that could be a possible size for the preservation station。

All right， let's keep going。How many AUs does the processor have？HOnce again， how many AUs。

 how many number of entries in the reservation station， all of these questions hint because。

You can only execute two instructions in parallel when you have the resources to execute them in parallel okay so either you would have reservation stations or either you would have multiple ALs so once again you have to figure out。

Which instructions are executing in parallel and executing in parallel means they have the E stage going in parallel okay。

 and I see once again， these two instructions hint that they were executed in parallel because their E stages overlap to some extent。

It doesn't matter that an instruction was killed， the fact that it was scheduled and it was in the ALUs means that the system has the capability to execute two instructions in parallel。

 okay？Allright。Things are sort of making sense， but so we are not done with the questions。

Is the anteor AL pipeline that's that's fairly simple。

Piplining means does the ALU take more than one cycle to execute the instruction？Yes。

 I see this move instruction that takes four cycles。

 I see this multiple instruction that takes three cycles。

 I see this oddd instruction that takes three cycles for the earliest pipeline。O。分开。Yes， yes。

 exactly。Yes， you're right， but you break it down into smaller cycles so you can execute multiple instructions in parallel。

 You're right， Okay， maybe I missed that I should have explained that。My bad。Okay。干不。关。ok 嗯。

I'll try to update the mental model for that but let me keep going and let's discuss it afterwards if that's okay。

Yeah， thank you for the。Question all right， does the process perform branchch prediction？

We saw that this is there are some instructions getting squashed and we saw that these instructions were preceded by a branch instruction。

That means that most likely the process of just performed branch prediction。是。O。

And now we come to the last question， at which pipeline stage is the correct outcome of the branch evaluated？

Now。At which outcome。When the correct outcome of the branch will be evaluated。

 that is when the next instructions will be squashed。

Outcome evaluation implies that I know where this branch is going to go。😡。

And as soon as I know where the branch is going to go。

 I can decide if my earlier path was correct or not。

That means it is the point at which these next instructions were killed。

 that is when the outcome of the branch was decided。

We can see here that this branch outcome was decided at this right stage and exactly at this stage these two instructions were killed。

O， so。Great， yeah， we have have we have gone through the entire question very carefully。

 we have first of a mental image of what you're going to do。And yeah。

 now we can just start filling in the answers and it was。

 I hope it was very clear on what what I was trying to do here and how to approach these type of questions。

O， so。What is the cash shift latency？Once again， let's take a look。你说。2。

They saw two load store instructions。Both both of the instructions hit the same address。

 that is why I can infer something about their cash accesses。The first instruction took eight cycles。

 the second instruction took one cycle， that means cash hit latency is。one。fi度。

What is the cash mislatency？I saw that this instruction rateed eight cycles。

 so cash miss would be eight cycles。What is the cash line size？In the mental image that we built。

To infer the cacheline size， you would need to change the address of the memory that you're looking at。

We see that at any point in the program we are always accessing r0 r0 is the memory target and we never change the value of r0 r0 is not。

😡，The destination for any of your ALU instructions。

That means I cannot tell whats the size of the cache line。Now。

 one more way that I would like you to think about this if you read if you read it more carefully right。

 so this is some more description that is put in the question now。

Description is not put in the question for filling up pages description is always put there to help you solve the question let's take a look at what this description says this description says using the information above answer the following questions regarding the process of design okay if a question as more than one correct answer or a correct answer cannot be determined in mind using the information provided answer the question as specifically as possible。

It is intentionally designed to be weigh。Okay， do not expect to find exact answers。All right。

 that gives me a hint that， okay， there might not be an exact answer。

Use phrases such as at least our most and try to narrow narrow down the answer， All right。

If nothing can be inferred， write unknown as the answer。

The fact that this statement is present in the description means that the authors intended some。

 not always， but usually some question as unknown。So it gives you a hint that one of these questions was designed to be unknown。

 and we see clearly that the cache line size is unknown。O。

What is the number of entries in each reservation station？Now。

Let's take a look once again at the execution diagramiaph， we saw this already。

By the have one more tip。Why am I doing the same question twice because these are numerical questions in the exam you are extremely likely to make a calculation mistake。

By solving the same question twice， you are doing yourself a favor by eliminating the chances for any calculation mistakes okay it's very easy to be in the pressure of the exam and see oh this is seven and not eight and then you will write seven and you'll lose your points so yeah。

This is one way that you can avoid just solving it twice will cost you like five minutes。

 but it will make sure that the answer is correct。Coming back to the question。

 the question ask what are the number of entries in each reservation station now we were thinking about in our mental image。

The number of entries in the resolution station can be infer by the amount of instructions that are in the execution stage simultaneously。

In our execution diagram， we see。These instructions。

Have their execution stages overlapping to some extent？Okay。😊。

This one does not have the execution stage overlapping。Okay， this one also does not have so。

These are the only two instructions which can give us hints about the number of。

Reservation stations are the number of AUs。ok。Now we have narrowed down where we are supposed to look for the answers。

Now these two questions are sort of similar， so in this case， either you can have two entries。In the。

In the。You can have two entries in this AU reservation station。Or you can have two As， okay。

 both of them are possible answers。Weion asks what is the number of entries in each reservation station。

 once again， careful greeting each， remember that we had two reservation stations？

You need to answer what is the number of entries in the memory reservation station？

Coming back to the concept， how do you determine the number of entries in the memory reservation station and look for instructions which have the overlapping execution units。

But unfortunately， I don't have any such instruction。 Unfortunately。

 I saw that all of my load stores are preceded by other instructions。

 So it is very difficult to determine this。 In this case。

 you can say that the number of in number of entries in the reservation station for。Wow is unknown。

All right， how many air news does the processor have？

As we just deuced from these two instructions which were concurrently in flight。

 either we can have two reservation station entries or we can have two AUs。

How many a use does a processor have？Potentially。wo。A use。

 we don't know exactly for sure we would need to see a larger history of execution to make an exact estimate。

Finally， the next question is is the integer ALE pipeline？Yes， thank you your earliest pipeline。

 because we have these。The E2 stage， once again， let's zoom into this part。

Why do I say it is pipeline， first of all， this is a branch and this is a mu。

And I know that the ale you。I apologize for the first movement。Yeah， yeah。

 and I know that the AU is responsible for executing the branch。



![](img/a353d04db1d832c56a5c2639e9019930_9.png)

And the mo。And I see both of them。In flight simultaneously at this point。That means yes。

 the AU is indeed pipeline because it is able to。Can we do it afterwards right so yeah。

I would be happy to help you get this concept right， but please let me finish this。All right。

 does the process of perform branch prediction？We saw clearly。Some instructions got squed。Once again。

 the tip to remember squashing means dynamic execution， dynamic execution can come from load stores。

 branch predictors， load value predictors， some other arbiters， but usually it is branch predictors。

So yes， we do perform branch prediction and our branch prediction went wrong。Yes。

At which pipeline stage is the correct outcome of a branch evaluated。

The concept associated with this question was。The branch evaluation is committed at the W stage and when I know that my branch is not going to be taken at the W stage。

 I will kill the subsequent instructions the subsequent instructions that are preceding this that were both killed were killed immediately after the W stage so at which pipeline stage is the。

Is the correct outcome evaluated， that would be W stage。O。😊。

That sounds good we just got 32 points perfect now let's take a look at how do I get the rest 18 points。

Oh， I see this one more simple。Not not simple， but okay once again。Don't panic， just' relax。

Read my instructions carefully。What is the program that is starting instructions？

That lead to the execution diagram shown in table3。

Fill in the blanks with the known instructions of the program。

And also show where and how many instructions are there in the program。嗯。

The question asks us to read the execution diagram and try to predict what was the original program。

Now why can the program execution sequence change the program execution sequence can always change because of branch prediction。

 because of function calls， because of changes in the instruction pointer。

I see that there were no function calls in the execution history given to us。

 I see that there were no changes to the stack pointer or to an instruction pointer。

The only confirmed change that I saw was this branch jump， which was wrong。So。

This gives me a hint that most likely this was the exact sequence of the program with the exception of these two parts。

 with the exception of these instructions。 These might be the。Trickty ones to get right。

 but otherwise。Since I know that there was no change in the control flow。

 the control flow change can always be affected only via function calls or via stack pointer or via instruction pointer。

 I know that I can copy them directly to the answer。Okay， let's， let's， let's do that。

 So we have this。冇。😮，Are0。0ero x 1000， okay， then we have a load。R1。To r0， al right。

 then we have a branch if less than。R1。Okay， now at this point I should try to take a look at the instruction semantics to figure out what would be wrong here because I don't know what this branch does I see a BL。

 this word means nothing to me until I read it。Let's take a look at the instruction semantics and what the instruction semantics say。

The instruction semantics for the branch instruction says that a branch instruction that conditionally takes the path specified by the label LB1。

 if the content of register R1 is smaller than integer value 100。Okay， so branch of less than。

To if branch if R1 is less than 100 to LB1。HThis is interesting。

Using the same semantics that we just saw， this instruction in the execution diagram says branch。

If R1 is less than 100 to LB1。All right， now I need to figure out where would LB1 go？

Since we know that the branch was。The the path that we took in the execution diagram was incorrect。

 that means at the end of the evaluation of the branch， we had to jump to LD1。Okay。

 that means that this LB1 label is where the program execution started after we squashed the instruction。

Remember that we squashed these two instructions and after that。

 this was the first instruction that executed to completion。

This is most likely where the label Lv1 exists。Once again， I'll repeat it just to make it very clear。

The branch will go the next instruction that is completed to execution after the branch。

 the correct address for the branch will be the instruction that will be committed。

The first instruction after the be。That we see is committed is W。This one， this， this， this ad。

 that is how I know what is the address of L1。Okay。

 so this means that these two were on the path these。

These mu and these store instructions were on the path that was not taken。All right。

 so if I think of this， if I think of the C code or this binary stream。

 I would say this would be an if。R 1， less than 00。If this is less， then， then go to。L B1。Else。

Else to this mu。And this store。Okay， so。At this point。

 we know that we also know that these two instructions were executed。But they were calculated or so。

In this stream， these instructions should come after the branch。Now， that means that at this point。

 let's let's， let's leave a little gap here since this part is a little。Day。

 we don't know what exactly happened at this point。

 but I know for sure that these instructions were executed afterwards， so they must follow。The bag。

Quantiply R1。R1。Aashtag 5， okay。Store。R0。R 1。 so we know that。The processor went。

In this path and then realize oh no， this branch is supposed to be taken。 So I have to jump to LB1。

 So this would be LB1。 And this is where the next instruction。This， this one would be pushed。

 This would be。Add。R1。20。R1， okay， and store。R 0。21。All right。

We don't know which other instructions were here。 so the reason I left these gaps is because these two parts are hazy。

 we don't know， so it might be possible that there were some more instructions here which did not enter the pipeline。

Some instructions here at this point。This did not try to the pipeline。And yeah， we just don't know。

 So yeah， it's it's， it's okay if you don't put this， but yeah， this is like。

The best guess that we can make for what happened。All right， so yeah。

That brings me to an end to this question。Once again， I'll quickly repeat the tips， negativety bread。

Read the questions carefully， okay， read the questions first。

Form a mental diagram so that you understand what's happening and image really helps you visualize if you can visualize it。

 then you can solve it。And then finally solve for answers。And。Yeah。Questions are going to be solved。

The answer is always in front of you， you just need to understand where to look for it。And yeah。

 I wish you all。A very good luck。And now let's take the questions that you had。哎原。咁点快家六点钟。嗯。你。

Can you come again， please？Yes。喂，诶咁样你。没有没题。嗯。关是这个。嗯。等有下。Okay。真持。一多年。你。呢日几你。因此。这个。诶啊啊。

It does not defeat it because your reservation station size might be limited。嗯白。Yes。

 that is very much possible。So yes， youre absolutely right。

 you understand so now I can see that you understand the concept of reservation station because you need a large reservation station to extract the parallelism that gives you performance improvement in auto of border execution。

If your reservation station size is one， then yeah， just do it scalar， just do it。

In order're absolutely right。Right。this operate to6 to any time of the not。Right。

I think that is because you see the first instruction move。Move and DL are simultaneously in flight。

So。嗯。Right， so okay， let's take a look at instruction one。

Instruction one completes execution at the seventh cycle， the commit happens at the seventh cycle。

After that， I have a load instruction。The load instruction will go to a different reservation station。

 remember that we had two reservation stations。Two Q is basically so the first Q has the move。

 the second Q has the load， the third instruction BL would go to the first Q。And at that point。

 the first queue gets full。And then you have the mu， which is also supposed to go to the AU。

 but I cannot send it to the AU Q because that queue is already full。对家都是结束。对。HT8十。Yes。は。Thank。Yeah。

 that's a， that's a good point。 I need to take a look into it。 Yeah， okay。

 I don't have an answer to that。At this point， in this question。

 this is the best I could come up with。But you're right。

 I see a point and it should be shifted backwards。But yeah。

 I'm not fully sure why it did not go that way can any other TA help me with that？都没有。Yes。第次案不开时间。

大个 send咁啲。It can also be bringing to the。再来个。嗯。当最个。完了。放家加灯。哦。

We don't know which way the branch projector goes。That's like so we sort of see so the point of this question was that。

It was showing you that the branch predictor predicted wrong。

 and we ended up spending time wasting on instructions which did not matter。收。

The question sort of hints that。Can you come again like。

 do do you see my point can you or can you come again。Yes。Yes， yes。Us。You were right， you were right。

 and that is why I left this gap。は。嗯。No。呃，有为。But if the branch was predicted taken。

 then we would not squash it， right， if the if so。好。

You got to decide one if it's taken or if it's not taken。对。没是。呢边做咩 too。Yes， yes， so see。

 the point is that in any case，'s let's think of this as a branch。This is the taken is the。Not taken。

 And this is the normal execution stream now。What's happening is that。

My branch director said something， let's not get into the words taken， not taken。

 my branch director said something。Okay。Preter says2 x， I'm going to do x。

But then when the answer for the branch is available， when I know that the predictor was wrong。

 at this point， I have to get rid of what I did in this X。That means I have to， this is what is。

Stated in the question as sququaashed。And then I have to do what was the right thing to do。

The right thing to do is what will hint you at LB1。你个说。Yeah。有。他是。That's the possibility。 Yes。

 but okay， this is once again， this is getting。😀H。😊，Okay， I don't know how to say this correctly but。

You are right， I understand your concern you're thinking about edge cases， which is very good。

It's not an enough case， but you need to solve this question and move on right， you have 20 minutes。

So。😊，This question is meant to be solved。I see that you're trying to dig deeper， but。

Take what's written at face value。Because if the face value is wrong。

 then you can always appeal in the final exam。第24。嗯。

You could could you could name that as LB2 so you can always switch the labels around right you could I could say that the one that was quaashshed was LB2 and the other one was LB1。

You can always switch the label you're basically asking that this could be LB1。

But my point is that this could also be LB2。I appreciate your questions they makes sense。

 but yeah you need to finish it within 20 minutes， take it at face value。

 think of H cases when they explicitly ask you to think of H cases， usually they will tell you。Yeah。

 I hope this was clear and let me know if there are any questions。

For sure you're already familiar with this type of question because we have it frequently in our exams。

 but it still is good to solve it and it's good to go over the question completely and comment a little bit about it。

So this is question a， GPU some Cindy， the question says we define the CD utilization of a program that runs on a GPU as a fraction of Cindi lanes that are kept BC with active threats。

During the rung of a program， as we saw in lecture and practice exercises。

 the CMD utilization of a program is computed across the complete rung of the program。

The following code segment is run on a GPU， a warp in the GPU consists of 64 threads that's important。

And there are 64 Sim delays in the GPU， so what that essentially means is that when one warp executes one instruction。

 the instruction takes one cycle。Remember that in the GPU lectures we covered as well。

 you the cases where the warp size was greater than the number of lanes and in that case we would need to schedule the instruction across several cycles。

But here is just one cycle。Each thread executes a single instruction of the sorry。

 a single iteration of the shown loop。That's also important as well in total as you'll see here。

 there are 4096 iterations， so what that means is that we are going to need in total 4096 threads。

Assume that the data values of a array A and V are already in vector to registers so that。

So there are no loads and stores in this program so for example here you have this instruction two as you see there are indeed two memory accesses。

 two reads right A of I and C of I and then one finally one right but we consider that this is a single instruction we consider that the values that we are opera input and output opera that we are going to use in this question already in registers so we ignore those accesses to global memory of the GPU。

Both A and V are a arrays of integers he noticed that there are six instruction in each thread right they are clearly marked here。

 so again the same for the if statements here we are considering just a single instruction for each of the statements。

Okay， so let's well also very quickly as I mentioned earlier there are 4096 iterations here so that's the number of third that we are going to need and then in the body of the four loop we have two E statements。

 one of them is checking if B of I is lower down 8888。

And the other one is checks if that value is greater than， right， so observe that is。lower。

Or greater， right。Now the exam says the question says， please answer the following four questions。

 so let's go one by one。First one is pretty easy。 We always have this question in this type of GPU and Sdy question and it's a kind of three points。

 The only thing that should be clear for you is that the total number of iterations is going to be the total total number of threats that we need and what's the number of threads per warp right and that's information that the question gives us so what's the total number of warps。

Is equal to。你多得。Number of threats。Divided by the number of。Threats。Purwarp。So this is 4096 is。

2 to the 12。64 is a number of threats per warped as two to the6。

So this means that the result is2 to the6， so in total we need 64。Warps to execute this gold。ok。

I guess no questions here。Anyway， feel free to raise your hand if you have any question。Okay。

 second one， it says we measure the C utilization for this program with one input set。

 we find that it is 34 over 320 what can you say about as A B and C be precise and look at the if branch is the hint that we are giving here so we have three arrays right and we are being asked about three arrays A B and C so if we observe the code and we observe the if statements we see that the only important so the only array that is important to make controlflow decisions is array B right so there is no impact of the values in arrays A and C that affects the execution of this program right so what can we say about。

A and C， we can say nothing。We cannot say anything about them， right。

 because the execution of the program and the total sea utilization is going to is not related to the contents of A and C。

But how about B， so clearly the values in V are important right because it's so here in the instruction one。

 we check if the value in V is less than something in instruction five。

 we check if it's greater than something right？So let's think about how someone who has calculated the CD utilization for specific values in array B has。

 let's say a reason about the calculation we know that the C。

Util utilization is equal to 34 over 320 right and here we can probably do different things we can reason here in different ways but I'm going to take advantage about the take advantage of the fact that I'm giving this I'm given this number right and if I see this fraction here。

 I see that in the denominator I have 320 and 320 is。一个。2， five times。64， right？

And remember as well that when I calculate the same utilization， what I。

What I have in the numerator is the number of instructions that are reallyor the number of operations that are really executed。

 which means that， for example， in one of these instructions is only executed by one thread in one warp。

Then the value here and the numerator is one。But if I have 64 threads in each war。

The maximum number of operations per warp and per instruction would be 64 right so 320 is five times 64 I'm going to assume here as well that all warps are doing exactly the same that's usually the normal thing in this kind of exercises and I know that five instructions are being executed in total right。

And the only way to execute five instructions in this code is by having threads that go through the first。

 the body of the first if a statement， right？And then these or some of the threads will or actually all the threads will also execute these instruction five and none of them will execute these instruction six that's the only way of executing only five instructions in this code。

So now we know that。A certain number of threats executed instructions。

 one to five and no threats executed executed instructions， instruction six。

Are there any questions here？ok。Now I can also see that all threads。

 all 64 threads of the warp execute this one。And this one， right。

 because before deciding if you go to the body of the a statement or not。

 you have to evaluate the condition right， so everyone does that。

So this means that two instructions are executed by the 64 threads of the warp right and then there are three more instructions。

2，3， and 4 that are only executed by some threats。 I know that it's not all of them because if it was all of them。

 then here I would have 320 as well， right， but it's not 320。 So only part of the threats。

Let's say let's called this number T。Is going to execute these three instructions。You see。

So from here， you will obtain that T is equal to。Threats。And what this means is that。There are。2。

 every。64 values。Actuallyly， consecutive values。Of B。are。Les than this number。The rest。R。

Exactly the number。Is it clear？No questions。Okay， good。So then for the rest of the question。

 we are going to reason in a very similar way， right， so the next one says let's put it。

Like this okay the next one says Part C says what needs to be true about RA B to achieve 100% utilization show your work be precise and complete and that it's important to be complete right so you may be able to come up with more than one possible solution and here we are asking you to be complete which means that you have to give us all the solutions the warp scheduler does not issue instructions when where no threads are active this is something that we assume earlier as well。

So there are three possible answers indeed and but the very first thing that is important to achieve 100% utilization is that all threats in the warp do exactly the same thing all the time right there is no divergence and there are three possible ways of not having divergence in this code。

 the first way is that all threats。Only execute these Eve， including the body plus instruction5。

The second possibility is that all of them execute this instruction and then these two instruction instructions。

 but not the three in the body。And the last possibility is that。

All 64 threads in each war only execute this instruction and this instruction。

 but none of the bodies because the values in B are all equal to8，8，8，8 right。

 so these are the three possibilities。 The first one is。All64。Concutive。Values。Of B， R。eququal。This。

Or all of them are。Less than this number， or all of them are greater。D this number。Make sense。

Of course， if you check the code， you'll see that for each of these three possibilities。

 the total number of instructions is different， the total number of executed instructions is different。

 but we are not measuring the number of instructions。

 we are measuring the utilization that right and we average the utilization over the entire execution of the program。

Okay， yeah， next question is what is the minimum possible S utilization of this program？

 So we already know what's the maximum is 100。What's the minimum。

But before you know I mean in order to do part C you have to do part E first right because in part E we were actually asking about what needs to be true about a array B to achieve the minimum possible S utilization show your work please cover all cases in your answer in case there are more than one case we only came map with a single case and in this case what in that case what happens is that we have as much divergence as possible that's the case where do S utilization is a minimum right and we already know that in this code there are two instructions that are always executed by all 64 threads the two instructions are instruction one and instruction5 threads always evaluate the condition。

定ing。What is the maximum divergence that we can achieve for the rest of instructions？

For these three and for these one， for this this body here and for this body here。

 the highest the maximum divergence happens when only one thread in the war executes。

The corresponding instruction right， so here what for the minimum we are we are assuming or we are guessing that。

Only one thread。excuts these instructions， another one thread executes these instruction seek。

 and the rest of threads simply don't execute more instructions because their values are equal to 8。

888。Right。So so then， as I said， every。64。Conse， consecutive。嗯。Values。Of b。1 is。list down。62 are。一款。

And one is。Greater。Than this number。And。Now here I'm going to make use of this as space。

 even though the answer I'm going to calculate the answer of to part B。So here I calculate the cdy。

Utilization。S， what's the total number of instructions？Remember， that is six。6 times 64。

 Now remember that there are two instructions that are always executed by all threads。

 no possible divergence there， so it's two times 64。And now there are。

There is only one thread that executes instructions two to four， so this is。Three times one。

 and then there is only one thread that executes instruction6。So， this is。1 times  one。

So if you calculate these， you will obtain 132 over 384。

 so that's actually the solution to this part。Is it clear？

when you try to calculate what's the minimum utilization always try to think it's kind of a hint is always try to think about how to involve many instructions in the calculation and then for each of the instructions try to minimize utilization right so that's what we are doing here is because in total there are six instructions I want at least one thread to execute each of the three of the six instructions and this way the number in the denominator will be larger and the total utilization goes down。

客机。Let me know if there are any questions。Hello everyone and the last question we're going to solve this cash reverse engineering question。

 so let's first take a look at the description and extract all the information we need so first yeah this。



![](img/a353d04db1d832c56a5c2639e9019930_11.png)

sorrry， this呃。Cash is addressed by B。We have the following five different possible block size。

For possible sociativity， to possible catch sizes。And one final。

Thing is the replacement policy either least recently used or first and first shot。

So the only statistics we can get is like the hit rate。With like two sequences， two axis。Sequences。

And both of them have。Eight different addresses accessed。So the first sequence。

It has a head of one over two。 So this means like we have four hits。

For the second sequence three over eight， so we have three hits。

And then the next paragraph is very important， it says that the cache is initially empty before the first sequence。

And the two sequences are executed back to back， so this means that at the start of the second sequence it will see the cache as it is in the end of the first sequence。

Okay， so the first question is to reverse engineer the block size。



![](img/a353d04db1d832c56a5c2639e9019930_13.png)

To do this， we can。Oops， to do this， we can try to group。So first we look at the first sequence。

 then we can try to group the addresses in like in increasing order。Zeros， 32。73。128。196。2， five，5。

8K。And 16 k。So we can immediately observe that no block sites smaller than 64 is possible because like theyre at least 32 bys apart。

 so if like we have block size of 8， 16 or 32 there would be no hits。And for 64 bytes。

We would possibly have this like this 32 will be a hit。And then。嗯。

Then then we would have like a hit here。So yeah， that's only two hits。So。

Now we only have one option left which is 128 bytes let's also verify that so for that we would have a hit here。

A hit here。呃。So that's like one， two。嗯。Three， four， four heads yeah so。



![](img/a353d04db1d832c56a5c2639e9019930_15.png)

The cash block size would be。128 bytes。Then let's take a look at the second question。

 so we would like to know the sociivity of the cash。



![](img/a353d04db1d832c56a5c2639e9019930_17.png)

![](img/a353d04db1d832c56a5c2639e9019930_18.png)

So as the sorry， ask the。Description already specifies。At the beginning of the second sequence。

 it will see the state of the cache as it is in the end of the first sequence。

So in the end of the first sequence， we will have the following cash block。So starting from now on。

 I will just use the starting address of a cash block to represent that block。

So let's say if I write a zero， this means like bytes。0ero to 127， like it's in this like cash block。

If I write one。So if I like write 128， then like it's like 128 byte to 255 byte。

 so yeah we will be using this notation for simplicity。So at the end of the first sequence。

 as we can see from our results for the first question， we would have Caline zero， Caline 128。8K。And。

sixteen k。

![](img/a353d04db1d832c56a5c2639e9019930_20.png)

OkayAnd then let's take a look at。The second sequence。嗯。So we can yeah and。



![](img/a353d04db1d832c56a5c2639e9019930_22.png)

Let's also， yes。So this would be a the address。And also， let's try to。

Try to know like what set this address could be so like I put an asterisk on the set because like it might not be the actual like set bits because we don't know like how many set it has yet but what we do is to divide these address by then like by yeah we remove all the offset bits from these address because we already know the block size is 128 and what remains will be used to address the sets so like these information can help us in determining like what are the possible socialativities so if we。

Divide all of these by 128， we have like zero one。This one would be 64。This would be 128。

So we can see that。呃D。对。And this address， they will map to the same set。

 regardless of the cache size and or like a sociivity because like they're both yeah。

 multiple of two。

![](img/a353d04db1d832c56a5c2639e9019930_24.png)

And then let's take a look at the addresses accessed by the second sequence。



![](img/a353d04db1d832c56a5c2639e9019930_26.png)

So。Let's see like let's say S2 sequence 2。The addresses would be so 127， this would be zero。4K is 4K。

8K is 8K。32 k， 32 k。196 is 228。And let's also have the set address。0ero， 32，64， this will be 256，1。😔。

And for the next trustees。Have 16 k。This 128。0，0。5，12， four。Okay， so。As we can see here。

 except for like。So we can know for sure that like this axis sequencing S2 will not replace。呃。

The cash block 128 because yeah like it's in set one and no other sets set asterisk value in sequence2 could consecate with it。

 so we have a guaranteed hit here。So because for S2， we have a total number of three hits。

 then the sosociivity must make like the。Number of hits in the rest of。Like these aes to be two。And。

So first let's take a look like a sociivity of one if like it's a sociivity of one then it's like a direct mapped cache so like all of these accesses would conflict so we would have no hits。

So yeah， then we roll out that possibility， then for the associivity of two。

 this means that like in a set we can have like two possible slots to put cash blocks。

Considering like we only have our lease recently used or first being first out replacement policy。

 you can see it very clearly that because they are like no aes that are like very close to each other that can。

Generate a hit with these two policies。Associivity of two is also like roadout yeah say to save time like I won't write it out but I think yeah it's pretty straightforward to see that if you just like try both replacement policies and then finally for sociivity of eight this means that like for a set we can have like eight different cash bug in that set at the same time so if that is the case then。

Yes， starting from the first axis， we would hit here。We would miss here， we would hit here。

 we would miss here yeah like now we。And we will hit here now we already have like four hits in this case。

 so it exceeds three so yeah we。Then we are only left with a possible sosociative value of。Four way。

Yep， and then for the third question， sorry。For the replacement policy。So we already know that our。

Cash block。That's 128 by。The soativity is。4our way。嗯。🤧Oh。Yeah， excuse me Okay。

 so then let's enumerate for both AOU and first things。

First of case to see which one can generate the desired result that we produce three heads in the axis in sequence2。

So to reiterate at the end or let's say at the beginning of the second sequence。

We would have like address zero， address 8k， address 16 k in the cache for the four says zero。

So for the first access。To to zero， it will。H in the cache and for the second access to 4K。

 it will miss and it will insert another。Ling this。4K line into the set。So。

And then for the next axis 8K， it will hit for the next excess 32K。

 it misses and it is going to replace a cache line in this set。

So if it is the first in first out policy， it will replace zero， so we end up with the sequence。Okay。

Then for 128， it's in the first step， so we ignore that。And then okay， for this 16 k。

 we will hit here， so we have like yet again four possible hits。1，2，31，2，3，4。

So this contradicts with the number the hit number of screens。

 so we only end up with like the ARU policy and see it and to see it for yourself， you can like just。

Go over this process again， but with the ARU policy。With the LRU policy。

 when this 32K is inserted into the set， it will replace 16 k。Instead of like zero。

 so for the next access to 16 k it will miss so yeah， then we got a final hit number of three。Okay。

So oops。Yeah。So then for the next question。

![](img/a353d04db1d832c56a5c2639e9019930_28.png)

嗯。

![](img/a353d04db1d832c56a5c2639e9019930_30.png)

We want to reverse engineer the size of the cache。In order to do this。

 we design a following access sequence consisting of three addresses。

 first access like 8K and then x and y， so our goal is to come up with the address values of x and y such that after this sequence we can know how many bytes are there in our cache。



![](img/a353d04db1d832c56a5c2639e9019930_32.png)

Okay， so the sequence is。8K。X and then Y。So at the end of the second sequence。

We would have the contents in the set as。Let me think。Z。😮，Yeah。8ight k。16 k。And。4K。Yes。And the。Oops。

 sorry， let me think。😔， yes。Sorry this should be this so yeah。

 because for the areaial policy this would。Yeah， replace the zero as we access it here。So。

In this case， at least the ARU bit。呃。Would be。So due2K， I have to be access。Address 8k in this like。

Probe sequence。So because there are like only two possible sizes， 4K。ABte or 8 k byte for our cash。

And we already know that like our cash is 122 byte block size。And four Was said Associative。

So this means that for four。Kaybytes。Um。One that would be。OneK large so。

All the addresses that are like multiples of 1k， they will hit in the same set。And for8 kilobyte。

Aud the addresses like that are multiples of 2 k they will hit in the。Same set so because。Like。

This access sequence。Brings the A U bit to this。32 k。And。

The way that we can know whether the size of the cash is 4K or 8K or not is to see if we can。

If we can replace this。呃。Leasst recently used。😡，Cashline， so in order to do that， we put why as。

3ty2 k。Such that FY misses。Then we know this。呃。Then like a previous address。

X has replaced this3 address， so in order to。Do to do that， we can set like X as。

X is like an odd number。An art multiple。😮，offff。Of one k。So in this case。

 if the cache size is4 kilobyte， then this axis of x would replace。36 k。嗯。

And if the cash size is like 8 k。Then this。Od sequence were not。Rep。So is it okay？

And it would go to like another set。So the axis of Y to the same address would hit。

 so by doing this we can know whether our cachelight is 4K or 8K。Yeah。

 so that solves our last question。

![](img/a353d04db1d832c56a5c2639e9019930_34.png)

是。So this would be。X would be 2 k minus-1。Yeah。4K。呃。Positive in？Why would be。So did okay。Yeah。

that solves all the cash。

![](img/a353d04db1d832c56a5c2639e9019930_36.png)

Problem， is there any question about this？Okay， so the next question is on branchch prediction。

 I will very quickly read the question。So here we have a processor that implements an in order pipeline with 15 stages。

 each stage completes in a single cycle， the pipeline stalls on a conditional branch instruction until the condition is evaluated。

 but we don't know at which stage the branch condition is evaluated and we need to answer the following questions。

In part A， there's a program with 20500 dynamic instructions that complete executing in this many cycles on this processor。

So if 500 of those instructions are conditional branches。

At the end of which pipeline stage are the branch instructions resolved。Okay。

 so yeah we basically need to find that in this part and we assume that the pipeline does not stall for any other reason like traditional branches and examples for data dependencies during the execution of the program okay so like the only reason for a stall in the pipeline are the conditional branches。

Okay， so how do we calculate the cycles right for a given program it's basically。So， let me。然后。Okay。

 right it here。 so we can。Cly the total number of stakeholdersples。

With the simple formula right so like first is the number of pipeline stages so assume you have only one instruction that you need to execute in this processor so it will execute exactly in 15 cycles because like the instructions you'll go through every of the pipeline stages if you have two instructions then these two instructions will be executed in 15 plus one cycles right so and you can generalize this as so even we have like and in a program with n instructions that program will execute in 15 plus n minus one okay so you do minus one because the first instructions included in these 15 cycles and then we assume n is the total number of instructions that are in the program to execute。

Okay， so here we can replace n with the number of dynamic instructions given in this part A。

 which is 2009500。 Yeah， so this is basically。Yeah， the formula that we will use。

 plus we need to account for the bubbles introduced by waiting for the branch conditions to be resolved。

We have 500。Yes。Conditional branches and then we don't know exactly how many bubble table introduce and for now like assume every branch instruction is introducing X bubbles and then we have 500 of these instructions so we can here replace the total cycles with the given program execution time which is。

4514 cycles。And yeah， so here， when you do the math， here x should be equal equal to four。Okay。

 and four is according to this equation， the number of problems right so it here be careful the question asking at the end of the reach pipeline stage。

The branch instructions are resolved， and then the IU should be at the end of the fifth stage。

 right because it introduces four balls。So assume so the easiest way to like check this。

 whether it should be 405 is to like think about the simplest case where the branches are resolved in the first stage right so like if the branches are somehow result in the type stage。

Then there will be no bubbles right so like in the first stage zero bubbles so then basically yeah the number of bubbles caused by the branch structures are the stage at which the branch result might one。

Okay诶。Yeah， this was part A。嗯。Yeah， I will clear this。nice scroll， okay， so in the second part。

 we have a new higher performance version of the previous processor that uses a mysterious branch prediction mechanism。

And with this new processor updated processor， the following code here executes in 136 cycleholes。

Yes。Okay， so here it says like everything else is this same about the processor。

 so we found that the branch conditional branches are resolved at the stage so we can use that information in this question Okay。

 the first question is，How many instructions will be executed when running this piece of code and show your work？

So let's first try to understand what's happening here so we have the register R1 which is initially zero so this first instruction just writes zero to R1 and then there's a branch that will jump to last。

When r1 is equal to five so initially r1 is not equal to five is zero so we move on to the add instruction the add instruction adds one to R1 and then we move to the next instruction here we have like a second register R2 which is zero so we continue moving on inside this part that starts with the loop two label and here again we have like branch equal instruction and here R two is initially zero and compares it to five。

Rich is。Like our is not five， then we don't jump to loop one， which is the beginning here。Instead。

 the program continues and R2 is increment。And we jump back to so this is unconditional branch right So like this is just direct branch as annotated here to loop two Okay。

 so like when you think about this here， what happens is this part is executed five times。

This is because like we started R2 at zero and then we don't take the branch for when R2 is 0， one，2。

3 and4 and when R2 is5。We reate this branch and jump back to loop one okay so this piece this part of the code is executed like all these three instructions are executed five and then we exit this part by executing this branch equal instruction one more time right it is finally taken。

Okay， so the same logic actually applies to this loop one part。

 so when you think about it it's exactly the same thing as loop two。

 but with the difference that like after going to this part once。

We execute loop two five times five plus one1， let's say， well。

 five times the tree instructions and one more time the branch instruction to be more precise。Okay。

 and but like these three instructions also execute pipeline as in the group below。

 and when this branch before is taken， this is the last iteration of the loop。

We exit loop1 and then move to the last instruction here， which just assigns one to r1。Okay。

 so let me complete here the execution counts of each of these static instructions。嗯。Yeah， so。Okay。

 so basically。Yeah， this is what the program does and then if you calculate the total number of instructions executed here。

 it will be one。One is this first instruction here， moving zero to R1。And then。

This part is a bit tricky right， so five times we will enter loop two and loop two is consisting of like five times three instructions plus one。

Okay， so five times we will go from loop one to loop two。

 which will be like 60 instructions here in the。嗯。And then five times we will execute these three instructions of loop1。

And I will do plus one for this。For the last execution of this branch over here。

Which will make the program jump to be less instruction。Okay， and I will do plus one one more time。

And then here， if you do the math， this should be equal to3 plus5 by 16 plus 15。Okay。

 and then this is 80，95，97。 Oh sorry，98。Okay， so this is the total number of insert that we have。嗯。

If you scroll down to the second question， it says how many of them。

 how many of the instructions or conditional branch instructions show your work。嗯。

So calculating that is now much simpler because we know what the program does。

 so visible instead of counting all instructions， we will only count the brand equal instructions。

And yeah， so in the first part in loop one part， we execute the branch equal instruction five。

Plus one times。So like five times when the branch is not taken and once when it is taken。

And for loop two， the branch instruction will be executed， so you'll enter loop2 five times。

And every time we enter it， the branchal instruction will be executed at five plus one times。Okay。

 so six times in total。Okay， I forgot to put plus here。And here when we do the math。

 the answer should be36。Okay， so we have 36。Conditional branches executed in this program。Okay。

 and these are the answers to the first two questions。嗯。In the city。Okay。

 so I wanted to like to remove these calculations for now。

 let's keep them and let's keep read this part C， based on giving them information。

 determine which of the following branch prediction mechanisms could be the mysterious branch predictor implemented in the new version of the processor for each branch prediction mechanism below you should circle the congregagation parameters that makes it match the performance of the mysterious branch predictor。

Okay， so we need to understand a bit better like what this mysterious branch predictor is doing right so so far these two first two questions did not reveal any information about the branch predictor。

 but let's reveal some information by calculating how many mispredis the branch predictor did such that the execution of this program resulted in howtener the sex cycles。

Okay so it's the first formula that we use in part A。

 so we have 98 instructions in total right so the total cycles。

For this processor will be equal to 15 plus 98 minus1 plus we know that every miss every branch mis prediction will result in four bubbles。

 then we do。For multiplied by n， where n is the number of mispredictions。Okay， so here again。

 15 is the number of stages we have in the pipeline。

 so initially we fill out the pipeline and then we require one instruction at then and then we have 98 minus one more instructions plus we add the total number of mispredictions and multiply by four。

 which is the number of bubbles。Okay， and then here we can replace the total titles with13 to six。

 which is given in the question。And then。啊。Do the match。

 right so like this is kind 1012 plus four times。And。😊。

And then from here we find 24 equal to  four times10， and from here n equals6。Okay。

 so six misprodictions。So whatever this mysterious branch predictor is。

 it should result in exactly six mispredictions。In order to achieve one the six typess of execution time for this given program。

Okay。Okay， six mis predictions this is what we need to keep in mind for the rest of the question Okay I will clear all the drawings now。

And let's also quickly analyze here how the branch outcomes or what are the branch outcomes。

 so for the first branch we know that it will execute six times in total right and the first five times it will be not taken。

And then the last time which will be taken right we jumped to the last。

Instruction and for the second branch equal。Instruction， it will have the same behavior right。

 so it will be not taken five times and six times it's executed it will be taken。

So here one thing you need to keep in mind is that the order of these branches are executed so here once we。

Execute branch the first branch once。And it is not taken。嗯。

This second branch will go through all of these。Outcomes right。

 so for each single execution of the first branch， we will execute the second branch six times and then the outcomes of these six executioners will be five times not taken followed by one time taken。

Okay， cool so like these are the branch outcomes basically that well need to consider in the rest of the question and now it is good that these text moves as I scroll because like that we can refer to these outcomes as we answer the questions。

 okay， could this be this be the mysterious branch predictor and the example as a aesthetic branch predictor？

嗯。Okay， and then here we have two options， either predicting as always taken or predicting as always not taken。

嗯。So if you predict as always taken。As you can see like we all make many mis predictions right so like the first。

Okay， this。So the first branch here will be mispredicted。And then。

The next branches over here that should be not taken will also be mispredicted trying。

 so like during the first iteration we like mispredicted six times already and then only the last branch here will be predicted as taken。

Okay， and then the next thing。Like we exit this first branch。

 youll have seven mis predictiondictions which exceed the target of six mis predictionctions right so the static predictor。

It's not always taken。Right so or the mysterious branch particular is not staticly always taken。

 you know that for sure， okay， but whatever we predict always not taken。Well。

 then we will correctly predict for the first。Oops， that's not what I names。啊，Yeah。

 so like those not taking branches will be always critical predicted and then we will do。

One misprediction here for this taken branch， and then we will do this five times。

Because like we will execute， we will enter this loop two。

 if you remember five times after every execution of this nonta branch or the first branch。

 okay so from here we have five piece predictions。And for the first branch。

 the branch prediction will do one more mis predictiondiction。

For the last situationureration where the branch is taken。

 and in total we will have six mis predictiondictions。Okay， that's good。

 So this is exactly what we are looking for。 And then here we can say that。Yeah。

 so the minister's branch predictor could be a static branch predict with the always not take option。

 so here the answer is yes and the option that satisfies this the given requirements are always not taken。

Okay，Anyway， I'm not going to try anymore because it's。Sort of hard to remove。嗯。Okay。

 and then the next part is so it's the same thing， but here we are going over like different branch predictors。

 could this be the last time branch predictor？嗯。Yeah so here again we need to evaluate each of these options that we have so last time branch predictor what it does is it predicts the last outcome right so like inter previous branch was not taken this branch predictor will predict the next branch as not taken。

Okay and then here we have two options， the initial prediction direction can be either taken or not taken。

 this is only for the first branch。And then we can store this information locally or globally。

 so local means that every branch instruction has its own lighting。

One level of history right so like we treat the previous outcomes separately for every branch instruction by using the program counter。

To differentiate the two instructions， or the second option is like to use a global last time branch predictor where the branch history is shared across all the branches。

嗯。Okay， so just for this sake of time， I guess I will not go over these one by one。

 but here the answer is that it's like no matter what options here you take。

 the branch predictor will always make more than six risk predictions。嗯。And yeah。

 so here the answer is basically no this cannot be the mysterious trans predictor Okay。

 so if you understood how the last time branch predict work。

 I think it should be very easy to go over these outcomes and then see that this cannot be the。

Did the mysterious branch predictor Okay， maybe I will go over one example so assume that the initial direction is not taken and then we use local branch predictor Okay。

 so like when you look at each branch individually not taken the first outcome will be correct。Sorry。

 the first outcome will be correct or predicted so not taken not taken not taken and then so basically the first like all not taken will be correctly or predicted in this case and the only misrediction will be in this last T okay so here we have one misrediction for the first branch and for the second branch again the same thing except like we'll have one misrediction。

One mis predictiondiction at the end for is taken。And then the next time。

 remember that we execute the sequence five times right for the second branch。

 the next time we like return back to the first not taken。

 it will be mispredicted because the last time branch predictor predicted or did the outcome was a taken and then the last time branch predictor will or we will also predict this not taken the actual outcome not taken branch has taken so it will make one more mispreddiction。

So for the first iteration it will make one misrediction and for the every other iteration。

 you will have two mis predictiondictions。And it will make two mis predictiondictions for the next four iterations。

Or I should say next four times this loop2 is entereded。Okay， and in total here for this loop two。

 we make nine mis predictionctions， which is more than six plus we had one mis predictionion for the first branch。

Okay， so this was just an example of these cases where we assume the the branch predicts configure as initially not taken with local。

With local。History。Last time branch。Okay， Mo young。

The next branch predictor is backward taken forward not taken so this is simple could this be the mysterious branch predictor so let's look at whether these branches are backward or forward branches so this branch equal jumps to lost right so this is a forward branch。

But the second branch in loop two goes back to loop one， so this is backwards taken。Okay。

And then this predictor will predict backwards as taken and forwards as not taken。Okay。

 so here for the first branch， then we will have。Again。

 so this is a forward branch and it will be predicted as none taken。

 not taken and five times it will be predicted correctly and the last time it will be predicted incorrectly so we have one misrediction for the first branch。

And for the second branch， this is a backward branch。And。It has not taken five four or five times。

 so all these five times not takens will be mispredicted and only the taken path will be critical predicted。

 so we have five times misprediction。Okay so here don't immediately jump into the conclusion that we have six misredictions in total because remember we execute this sequence of five nine takens and one take for the second branch。

 five times in total so like here the total misredictions for the second branch will be five times five。

 which is 25 plus one。Okay， so then backward taken forward。

 not taken cannot be the mysterious crime predictor because we make 26 mis predictiondictions in total。

Okay。And then this is the last part， this is a two bit counter based prediction okay。

 just to remind you how this works， so we have like a two bit history and so this again can be either local like per branch instruction or global shared across branch instructions。

And how this works is initially we have some states， some starting state， either  zero。

0 or one of these four cases listed here。And so every time like an outcome of the branches is evaluate that the counter is incremented or decremented right so for example。

 assuming we are at zero0 and strongly not taking case， if the actual branch outcome is taken。

 then the counter will be incremented to zero1。And from that point on。

 the prediction will still be really not。But once we encounter one more taken branch。

 the counter will be inemented one more 10 to10 and from that point on。

 the branch predictor will start predicting the outcomes has taken right and then depending on whether the actual outcome of the future branches is。

Taken or not taken， we'll keep incrementing or decrementing the counter and making predictions based on the current value of the tubit counter based branch predictor。

Yes。Okay， so here are some configurations that work actually that result in six mis predictiondctionions。

And these are， so just like based on the solution that we provided for this question， these are yes。

Local or global doesn't matter。And these two cases where we start from strongly not taken or we not taken。

Okay， all these configurations result in exactly six predictions。So as an example。

 I can run one example， so this time let's choose the global mispredor。

not local and start but let's say strongly not taking place Okay。

 so that's sure to result in exactly six misredictions。啱。

So we take this as a starting point and a global predictor。Okay。

 so here you need to go over the branches one by one， the first branch is not taken。

 this will be correctly predicted and then the counter remains at zero zero and you don't have mis predictionction。

 then we enter this sequence of four， five nine takens and one taken。

All nontas will be predicted correctly and then will remain at0 zero。

And then the take branch will be mispredicted。And the contract will be updated to 10。Afterwards， the。

Go to this branch。 So I'm ordering the following the program order right。

 And then here we will have correct prediction。 although the counter is that once you remember。

 this is weekly not taking case。And the prediction will be still not taken。

 and then the counter will be updated to00 again after the B because outcome of this branch will be still not taken。

And then， yeah， so here we had one specific chair member for the first execution of this。

Sequence of the second branch。 And then。When we enter the sequence one more time。

 we'll have one more misrediction okay so I guess you see the pageant here。

 every time we enter this the sequence of five command take and one taken for the second branch we'll have one mis predictiondiction。

And remember we do this five times， so we will have five misredictions。And then yeah。

 so if you go over these branches， non taken branches one by one。

 and then finally when we are here at the final like。Instance of this branch， which is taken。

 we will again mispredt because like when we leave this sequence for the second branch， remember。

 we leave it when the counter is at 10， which predicts this taken branch as not taken and gets updated to 10 right but the。

Although we get updated later to week or taken state。

 that is before we make the misrediction before we actually do that evaluationally。

 so we get plus one misrediction from this first branch and in total we get six mis predictiondictions which is the number we are looking for to complete the program at the target 13 six cycles。

Okay， so basically for the。For the options that I marked initially。

 like no matter whether you start at 00 or 10 degree taking cases or whether you use local or global branch prediction doesn't matter or all these branch the branch predictor will make exactly six mis predictionddictions。

是。Okay， are there any questions or any cases in particular that you want me to evaluate here as an example？

Yeah， if not， I guess we are done with this question。



![](img/a353d04db1d832c56a5c2639e9019930_38.png)

Well done on sticking it out we only have one more question to go this question is on VLIW so very long instruction words let's go through the question first to see what we're dealing with so we are told to consider a VLIW CPU that uses the long instructions formats shown in table4 this is table4 and so we see that we have four slots for short instructions in this in each of these long instructions so that's what they tell us next each long instructions is composed of four short instructions however note that there are restrictions on which type of instructions may go in which of the four slots so as table four tells us here the first slot can only contain memory instructions the second one integer instructions control instructions and float instructions respectively for the third and fourth slots for short instructions。

嗯。😊，Then we have table5 table5 provides a detailed description of the available short instructions and the total execution latency of each of them each short instruction execution unit is fully pipeline this will be important so don't forget this detail and its result is available on the cycle given by the latency what that means is for example for a control instruction its results if any are made available for other instructions to use in the next cycle let's take a look here at the category control in in table5 we see that the corresponding latency is one so what that means is we issue the control instruction and then the result is going to be available right after right in in the very next instruction。

So the information that we need to get from this Staple5 is that we have one type control instruction which is the branch on sorry the branch if equal instruction we have a load instruction which has a latency of three cycles we have an integer add and a floating point add instructions also this should be very familiar they follow syntax analogous to MIPS so just keep these in the back of your of your mind we come back to them as soon as we need them so then we are given another table this time with a piece of code unfortunately you are going to be the compiler so you know that this is the code that was generated from some application however unfortunately this code contains sequence of short instructions so we cannot directly input these short instructions into the VLAW instructions and that's going to be your job for today。

So here we have table six， which you can see is the proposed code for calculating the results of the next Swiss referendum we're not really concerned about that。

 but our task is going to be to map each of these from one to 12 into basically。😊。

The instructions that are scheduled in the VLAW machine。However。

 before we get into that we have a warm up question so this warm up question asks us which are the following our goals of VLIW CPUU design and they ask us to circle all that apply the options here are simplify code compilation simplify application development reduce overall hardware complexity simplify hardware instruction dependence checking and reduce processor fetch width before we think about this I'm going to quickly borrow from some of Professor Molow's slides this is where the concept of VLIW was introduced I just want to call your attention to a couple of sentences here which I think will make it very very easy to answer this question first the idea behind VLIW machines is that the compiler should find independent instructions and statically schedule meaning packing or bundling these independent instructions into a single VLIW instruction crucial。

😊，Here， this is the role of the compiler。And then also this first point here。

 a very long instruction work consists of multiple independent instruction packeded together by the compiler。

 I'm just going to quickly scroll up here also。嗯。Yes。

 so a couple of slides back we also have these important sentences hardware fetches and executes sorry the hardware fetches and executes the instructions in the bundle concurrently and crucially also there is no need for hardware dependency checking Keep in mind this is because the compiler itself is taking care of this for you so there is no dependency checking on the hardware betweencurt concurrently fetched instructions in the VLIW model so with this in mind I think we can come back to our wormup question here is the code compilation any simpler not really this is not true in fact now there is added complexity because we need to take care to find these instructions that can be bundled into a single instruction is application development easier also not necessarily on the one hand there isn't even that much of an influence this affects the compilation process not so much the application development process but if anything it would become more complex because we need to take the microarch。

😊，ectture into account when when scheduling instructions， however， and this should be very。

 very clear from what we've just read。 it does reduce overall hardware complexity。

 So this one is correct and it does so actually the the fourth option here helps us it simplifies hardware inter instruction depend checking。

 We don't need to check for these dependencies between different instructions。

 We just need to execute them as they were scheduled right so it also simplifies。

The the the hardware inter instruction dependence checking does it reduce the processor fetch width not at all in fact the opposite right the fetch width becomes wider right we fetch more let's say bytes with with each instruction that we process right so this fifth option is also not true so the answer here for part a is sentences three and four。

Now we move on to part B now our task is to determine the optimal VLIW scheduling of the short instructions by hand。

 so we want to fill in this table that I briefly showed you before with the highest performance that is the fewest number of instruction cycles instruction sequence that may be directly input into the VLIW CPU。

and have the same functionality as the code in table6 so we're going to have to basically keep these two things on you know on our brains RA。

 we are going to need to keep this code that we want to map in mind。

 we're going to need to keep the latency of each of the operations in mind and we're going to need to basically schedule them as we can with the goal of minimizing latency。

Or rather with the goal of maximizing performance which is what the question states okay so where possible you may write instruction IDs which is what I'm going to do for the sake of simplicity notice that each of the instructions here is numbered so for the sake of simplicity I'm just going to resort to using these numbers in this table and we can also leave any not instructions notes it's likely that there will be quite a few not instructions because we're not going to pack the entire table and we can leave those as blank slots consider only one loop iteration including the back instruction ignore initialization and any cross iteration optimizations for example loop androll loop as a brief side note loop androlling is very very commonly used optimization technique especially in these VIW contexts so good for you to know but not relevant for this question they ask us explicitly not to consider that and also not to optimize the code by removing or changing existing instructions so let's。

Oh by the way we also have a hint on here that the entire thing should not require more than 20 cycles I don't think we're going to have that problem so let's start at the beginning which is I think when we're giving a sequence such as this I think it's a good idea to start from the top and to follow the instruction sequentially because this will also make it very clear where the dependencies arise arise basically so the very first instruction。

Is a load instruction？U。And because it is the first instruction and we were asked to ignore anything that came before the execution of this code。

 obviously there is no dependency here， So the the takeaway is that we can just schedule it as soon as possible right so now I come back to the table here and。

Of course we know that the load instructions are memory instructions and they have a latency of three cycles。

 so here on the first cycle I can place my first instruction。As I said。

 I'm just going to use the numbers here afterwards or maybe。😊，Concurrently。

 I can also show you the solutions sheet which I have here， which is prettier。

 but for simplicity and also to help me with annotating some things I'm just going to use the instruction numbers here。

Okay， we go back to our sequence of short instructions and the second one is also a load。

What does this load depend on， It depends on the value of R1。

 and then it loads whatever is stored in the memory address stored in R1 into the register R1 There's no dependency again。

 So what that means is we can just come back here into the table and just schedule the second instruction。

Right after the first one， why can we do this， notice that although the latency of the memory or in this case of each memory operation is three cycles。

We are also told this thing that I underlined here so that the execution is fully pipelined。

 what that means is。If I look at this first load， this first load starts in cycle1 and is going to take a total of three cycles to become available right so I can use the value that I loaded in the first cycle at the earliest in cycle 4 however。

 because its because the functional units are pipeline I can start a second load while the first one is still ongoing right so what that means is I can begin this second load here in the second cycle。

Great， so。The next instruction up is this integer add。

 Now this integer ad takes in two arguments R 0 and r1。

 and those are the values that we're loading in these first two instructions。

 The issue now is that these are not immediately available， in fact。They will only become available。

As I was just saying the value that we're loading in the first instruction because this is load instruction becomes available in cycle 4 and the available for use in cycle 4 and the one in the second instruction becomes available for use in cycle 5 and because the two values that we're loading are the values that we want to use right what that means is that the earliest though we can schedule this third instruction is precisely cycle 5 right when the second load becomes available。

😊，Awesome， let's look at the next instruction。 We have a floating point add now， this one。

Requires the values of R0 and R4 so R0。Is loaded in the first instruction I've already said it。

 I think three times now that becomes available in cycle 4。 However， this value。

 the value of r4 only becomes available after this i add complete How long does the Iat take to complete we scroll back up to the table and we see that the latency and cycles for these instructions is two cycles So what that means is this integer add that we started in cycle5 becomes available for use in cycle7 right5 is the first cycle6 is the second cycle and then the results is available for use in cycle 7 and I want to be really sure that I don't screw up。

😊，But so far， so good， what this means is。We can scroll here to the right all the way to our float column right because we'll remember the instruction that we want to do is a floating point at and that can be scheduled as soon as this integer edition。

 let me scroll zoom out a little bit as soon as this integer edition the result of this integer edition becomes available and that happens in cycle 7 so here we can go to cycle 7 and we can store our fourth instruction。

Great， so。Then we have another couple of load instructions note that these load instructions。

 the first one of them requires the value r2， there is no prior dependency with any of the previous instructions so this can in principle be scheduled as soon as possible and however for this second load word here so the one at index 6 we do have a dependency on our zero。

The the most recent instruction to modify our zero was the first instruction with a load and we again need to remember that this has a latency of three cycles so we want to schedule instructions five and six as I said for the first one not a problem we can just schedule as soon as possible right the earliest slots that is available in the memory column is this cycle here right and then。

For this one for instruction6， we want the value of r0 to be the value that we load in the first cycle。

 how long does that take to be available it takes three cycles right so this value becomes available here。

That's very good news for us right because what that means is in this cycle I can already schedule this instruction right maybe now is a good time to revert back to this this is the solutions which with much prettier font type than what I can do and so basically what you see here is that these fifth and sixth instructions can be scheduled here right next to each other。

 the R0 that we load from the first one is then used to basically for in this fourth cycle for the sixth instruction。

😊，Great， now we have a bunch of arithmetic operations that we want to take care of。😊。

We have a floating point add here， this one requires the values in r1 and r6 let's see so r6 was last modified by this load here and R1 by this load here so essentially we look at the latest load the yeah the latest load here started at cycle。

So this is instruction5。 we come back here。 this is instruction5， started here。

 and it's going to take three cycles。To to become available so what that means is。By cycle five。

 by the end of cycle five， we have all that we need。Or this floating point edition。

Since bycycl5 the value of r6 becomes known and the value of R1 was already known from from before okay so what that means is we have another floating point edition right this is going to be number seven the last one that we filled in was number six and the interesting thing is we can actually schedule it earlier then the floating point edition that we saw before right because we have everything that we need at this stage。

Cool， now。We have a bunch more integer editions， so let's see。This one here， instruction8。

Depends on R 2 and R 4。U。So let's see。Our four is modified by instruction three。Which is here。

 And we know that integer instructions have a latency of two cycles so。Based on this dependency。

 the earliest that we could schedule this instruction， this instruction8 would be。Here， right？

Exactly would be here。And then we look at the other dependency。UmW whichhich is。

So we have eight or two or two comes from load with label6 and that has a latency of three cycles so again same thing it would also be available here so what that tells us is that we can actually schedule the iad or so this instruction with index 8 we can schedule it here still matching up with the solutions which is great news okay next one our。

Instruction9 another I add this one depends on r5 and r4 so we just modified r4 in the previous instruction and r5 was last modified by this floating point instruction okay so we're just going to have to take a look at both of those the latency of floating point add is four cycles the latency of integer add is two cycles the okay so now I want to briefly make notes of the corresponding instruction numbers so we have four。

And。8。Right， so we have four。Here and eight here。 so eight has this one has a latency of two cycles。

Right and then this four has a latency of four cycles right so that's going to take one， two， three。

 four cycles so only here。Does this value from this instruction become available。

 what that means is I can only schedule this instruction nine。Basically at cycle 11。Okay， great。

 we have a couple more instructions to go， we have instruction 10。

whichch is going to add the values in registers six and two those were last modified by instructions five and six。

 these are both loads and so we can just take a look at those five and six。Here， right。

 So the the latest one of them is going to take three cycles。

 So that's going to become available for use here at this stage， right， however。

 note that we have already， so that the instruction that we want to schedule is an integer ad。

 and we've already scheduled an integer ad for for this point。 So what we can do。

Is we can schedule this 10 instruction for right after it， right？Okay。

Same logic here I think you got the idea by now so we have a dependency on our0 and on our three our three was last modified by this instruction 7 our0 was modified the instruction that comes just before so let's take a look at this instruction 10 this one has a latency of two cycles right so this value becomes available here at this point however。

We also need to consider instruction7 In 7 is a floating point edition a floating point edition has a latency of four cycles so starting our counting from here one。

23，4 the value becomes available for use here at this stage luckily for us that's the same as the other one so what that means is that this instruction 11 can be scheduled basically at any point after after this this checkpoint when both values become available so we can just schedule our 11 right there。

Okay， we've made it to the end。 We have one instruction to go a branch on equals。

 This branch depends on the values in r 0 and r 5。 R 0 is modified by this integer ad right before and our5 comes from a previous integer add。

 So we care about instructions now9 and。11。So the latest of which is actually nine right so these are all these all have the same latency because they're in the same column so we can just look at the latest of them and that's going to take two cycles。

😊，To become available and so what that means is that this final instruction。

 the 12th instruction I can schedule for right after that value becomes available okay。Cool。

 just for your reference， this is the final solution。

 This should look almost exactly like mine and I will highlight one thing which is the most eite among you will have noticed that this table actually has one more instruction than the one that I that I just filled in the reason for that is that if you notice this instruction 8 because nothing else depends on it can go here which is the earliest that it can be executed but there's also no harm in placing it here between 10 and 11 right that will not affect any later instructions and will not also not delay the total time to execute the program because this even if this instruction8 were to start two cycles later it would still be done before you know before the program reaches completion so what the official solutions give us is ideally this would be colored in red if this had been printed in color。

 but basically notes instruction。😊，mayy go in either of the red slots right so there were two right solutions here。

 this instruction aid could either have done here where I placed it when I was solving the problem or here and you know since that doesn't affect the total execution time。

😊，Cool， is everything clear up until now？Okay， awesome。

 so we only have a couple more questions to go， these ones should be fairly straightforward。

So how many total cycles are required to complete the execution of all instructions in the previous question。

 ignore a pipeline fill overheads and assume that the instruction latencies are the ones given in table five。

What we need to do now is basically see when the when the program completes so when is the latest point at which we complete a memory instruction all these have the same latency so i'm just going to look at the very last one and that one gets issued here and takes three cycles。

Right memory takes three cycles to complete what that means is we're going to be done with memory instructions by cycle6 let's do the same thing with these integer ones this takes two cycles so we're going to be done with all integer operations by cycle 12 we do the same thing with the control instructions the latency for the control instructions is a single cycle what that means is we're going to be done with these control instructions by cycle 13 okay so that's the latest one that we've seen so far so if we want the total execution we would use this one and we just need to check like we know that the float operations take a while let's see if that one goes past the branch and we see that the latency for that is four cycles so whatever starts here takes one to three four cycles and is done by cycle 10 so no the answer the final answer is that we take 13 cycles right。

To be done with the execution of the program。 So that's our answer here。

 What's the total number of cycles， The total total number of cycles is 13。 and now。

We want to know what is the utilization of the instruction scheduling slots computed as the ratio of utilized slots to the total execution slots throughout the execution。

 I have an important remark to do here which is that because there is no standard way to measure this kind of utilization it's very important that you read the question carefully So in this case I ask you to give me the utilization as the ratio between the utilization slots and the total slots。

 but this is not the only way that I could ask this I could ask between the ratio of utilized slots to the number of VIW instructions right you might see that in different questions on this topic So always be sure to double check how we want you to calculate the utilization if it's ambiguous if you don't know what we mean be explicit and state your assumptions right that's always a good idea in this case we are asked to compute it as the ratio between the utilization slots and the total slots that we had so。

How many did we use we used for here then one， two。

 three or five here right note that here one of the instructions is duplicated so four plus5 is nine then plus one here is 10 plus two here is 12 so there's 12 slots that we used。

That's going to be the numerator of the expression， right？

And the denominator is going to be how many slots we could have used， okay。

 and that depends basically on how long the program took to finish and since we know that the program took 13 cycles。

To finish， we know basically that there were for each of these cycles。

 I have four slots that I can use。 So I the total number of available slots is just 13 times4。 right。

 It's just literally the the number of boxes in in this table during the the run of the program。

 So here is going to be 12 divided by 13 times 4。Okay。And。If you do the math here， this works out to。

 yeah， basically three。Over 13， which would have been fine but。Because my cheat sheet here。

 this is approximately 23。1% okay， so in all these VW questions。

 this is a very common question to ask so it's good that you're comfortable asking for utilizations。

 yeah。是是。So if this cycle some disrupt stop。 we also overcome that as。

Yeah okay so just to recap the question for anyone who's listening online the question was and tell me if I answered it correctly the question was that at this 13th cycle there is still an instruction executing right and the worry was that it was it would not be done by the 13th cycle that's a very good point however this instruction has a latency of。

😊，One cycle。Okay， so it actually is done by the end of the13 cycle right so be careful with like this is the you know start from zero and the number of cycles this is always very tricky right but。

😊，We we take up the entirety of 13 cycles to be done and this one takes one cycle to execute right this branch on equals so it is actually done by the 13 cycle so that's why we use that in the in the denominator if。

 for example， if this had a latency of two then you're right you would have had to use 14 instead of 13 Okay。

 does that make sense Okay cool anything else。Okay， then I think we are done for now。

 all that is left to do is to issue you all the best for the exam and to encourage you to use the forums and all other channels that you already know of to ask for help。



![](img/a353d04db1d832c56a5c2639e9019930_40.png)

Yeah。😊。

![](img/a353d04db1d832c56a5c2639e9019930_42.png)