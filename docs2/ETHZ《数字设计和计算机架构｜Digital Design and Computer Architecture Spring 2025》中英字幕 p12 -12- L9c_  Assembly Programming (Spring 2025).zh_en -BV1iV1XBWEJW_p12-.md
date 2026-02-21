# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p12 -12- L9c_  Assembly Programming (Spring 2025).zh_en -BV1iV1XBWEJW_p12-

![](img/aa16fcc74ce514f2dd52a38c336477a5_0.png)

And we're going to look at LC3 and MIPS assembly and they're essentially very similar as you have seen so far with some idiosyncrasies in terms of the differences in instructions and these are the same readings that we discussed so basically we're going to look at some programming construct talk about debugging a little bit more about principles than actually real detailed examples because detailed examples are actually quite too detailed to cover in even one lecture actually but you can study the examples on your own certainly we're going to talk about conditional statements and loops that are important and then arrayse and if you have time we're going to talk about function calls if not you can study them on your own。

 but they're no different from function calls in any other ISA if you will so remember we' still talk about the one Neyman model。

 one Neman machine and instruction cycle these are things that you should keep in the back of your mind we're going to build our first LC3 program by using conditional branches for looping essentially and essentially we want to write a very simple program that has 12 integers。

😊。

![](img/aa16fcc74ce514f2dd52a38c336477a5_2.png)

![](img/aa16fcc74ce514f2dd52a38c336477a5_3.png)

And these integers are stored in addresses hex 3100 to hex 31 obB and usually the way you go about solving a problem in remember we're solving problems in computers and the first step is really translating the problem to an algorithm right and essentially to do that we actually create a flow chart of the algorithm in this case the flowchar or the algorithm is very low level as you can see because we're going to program in assembly later on so basically you can see that we even decided the register assignments so we're going to put the address of the first integer in 3100 over here we're going to put the counter in R3 and then we're going to put the number of integers in r2 over here。

😊，So our one is the initial address of integers as you can see our three will store the final result of the addition and our two is a number of integers left to be added right at this point so that's this is the initialization part almost always algorithms have initialization parts and that's what we're going to do over here。

😊，And then the first step is to test whether r2 is equal to0。

 meaning whether we have any integers left to be added， if it's not equal to zero。

 then we do the addition。😡，If it is equal to the zero。

 which means that we reach the end of all the integers to process。

 then we actually get out of the loop and do whatever else， maybe I'll put this to a screen。

 for example， right？😡，Okay， so basically are we done with all integers。

 that's what this is checking if we're not done， we load the first integer into a register。😊。

Remember that r1 specifies the address and that's doing the loading and then we essentially accumulate your value in r3。

😊，Increment the count or increment the address and decrement the count of integers basically and that's what it is and then you basically keep looping okay。

😊，So hopefully this is very similar and simple and you've already written some programs in your life in DTH for sure。

 but if you're taking this course as a first course。

 then this may be your first program to actually write but that's not true at ETH so basically the next step is translating all of these to instructions in the ISA and that's what this does this directly goes into machine code of course and we use conditional branches to create a loop and these are the instructions as you can see。

😊，So you can see that there's a load effective address that loads a value into 3100 and this is basically what we do in the instructions so this is the load address as you can see over here and then we reset the registers。

 the top two things over here R3 and R2 and then we initialize the counter as you can see over here R2 and then we basically check the condition that's over here and then we jump out if the condition is true if not then basically we execute this block over here。

 load the value in integers and then accumulate it and then increment the address you can see that different form of ads are use add register and add immediate over here and then decrement the counter of integers。

 increment the address we go to the next address and the next iteration and then unconditionally branch NZP is unconditional branch unconditionally branch。

😊，Back to loading the value right that's what we're doing over here or checking the condition sorry not loading the value because we need to check the condition first because that's our loop exit place so basically you need to get the branches right that's the key point over here if you're doing assembly programming you should not branch to here you should branch 30004 over here okay so hopefully that's clear right and you know actually exactly how to execute all of these instructions in the LC3 data path that I shown you earlier I'm not going to go through this in detail again but everything that we have seen in the previous program you've already seen in the execution of the LC3 data path。

😊，I see a hand raised， is there a question？I see a hand raised by Alexander。Okay。

 maybe it was a mistake， that's also a fight。If there's no question。

 then I will move on Okay okay so basically that was our first program and you know exactly how to execute every single instruction in that program。

 Now let's raise the abstraction level a little bit and talk about programming because based on everything we have seen right now now we know exactly how instructions execute we're going to show you more of that later next week now you know actually how to build programs that can execute on a real machine and you know how the real machine is built based on the combination and logic structures。

 So nothing is magic at this point。 Nothing really should be magic at this point in terms of how you can go from a transistor all the way to assembly programming And now we're going to close the gap for assembly programming So we're going to talk about programming from the high level So we have a task。

😊，And programming requires the get task in other words a units of work into smaller units of work so it's all of the programming is really divide and conquerque in the end and the goal is to replace the units of work with programming constructs that represent that part of the task that your're subtask let's say and there are three basic programming constructs sequential construct conditional construct and iterative construct and are。

😡，Our instructions are actually enabling these constructs， instructions in the ISA。

 so a sequential construct is kind of obvious you have it has to be decomposed。😡。

And you can break it down into subtest one following the other。

 so basically you break it out into two subtest so that you can think about the program in an easier way。

 let's say or algorithm， Okay， so hopefully that's obvious conditional construct is essentially enables you to do one of the subtest。

 but not both。😡，So it basically enables you to test a condition and based on the condition。

 execute one task and if the condition is not true。

 execute some other thing and clearly this is an if an else contrast right either subtask maybe do nothing after the correct subtask is completed the program moves onward if you will so you can implement if else statements or switch case statements as we have seen earlier and very log also implements these as you remember so iterative construct is used if the task consists of doing a subtask a number of times but only as long as some condition is true so this is used to implement loops as you can imagine first you basically test a condition if it's false。

 you don't do it if the condition is true then you do the top taskask it could be the other way around also you could actually test the exit condition also and if the condition is true you could exit the loop as well so basically it's a looping construct let's say and if the condition is still true you keep doing the subtask for loop by loop do by loop are examples of loops so let's take a look at these constructs and example。

I'm not going to go through this program in detail actually because we don't have time and it's I think trivial to go through it。

 if you will so the example program is going to count the number of occurrence in a character in a text file it's going to use all of the construct sequential conditional and iterative and we will see how tried conditional iterative constructs using conditional branches so counting occurrence of a character basically we want to write a program that count to occurrence of a character in a file。

😡，So we're going to get the character to search from the keyboard using a trap instructions that's going to be the novelty we will learn at the end of this but we're not going to go into how it's implemented and the detail of it or we're going to interact with the keyboard over here and the file will finish with the character end of text EOT this is a special character called the sententinel character。

 if you didn't know about the word sententinel it designates the end of something essentially in this example EOT is set to4 for example it could be something else output will be output result will be placed onto the monitor using another trap instruction essentially again you will see that but this is how I break my program into the construct sequential conditional and iterative again I'm not going to go through this in detail but you need to initialize account and you remember the constructs pictures over here you need to initialize account。

 initialize the pointer， get the input character from keyboard get the character from file that we're going to compare to the input character。

Then if the character that we got from the file is not end of text， then we keep looping。😡。

What do we do if we loop， we check at the end of file， if it's not the end of the file。

 we check if there's a match， if there's a match， we increment the counter of the characters that match the input character。

 if there's not a match we don't increment and then we get another character from the file and then increments the pointers and the initial address as you can see over here and then we keep doing the same thing until the character we read from the file is end of text。

😊，So that's the iterative construct and I already describe all of these actually and then if at the end we prepared the output。

 we exited the loop we're done with the file and we prepare the output to write don't worry about exactly what this means this basically convert the output to an ASI character that can be displayed by the monitor and then we output to the monitor and the monitor displays the character in its own format okay and then we halt the program using another trap instruction to stop the program because we're done essentially so this is a full program and you can read again the pattern Patel chapter that houses this program so trap instruction basically let's talk about trap instruction because it's important this is the operating system hardware essentially in LC3 MIPS as its own instruction it involvesvos a service call essentially the operating system service call it's in assembly it looks like this a machine code that looks like this is very simple basically and you have a trap vector basically。

😊，The op code is 11，11， and Tra Victor specifies what？😡。

YouWhat do you ask the operating system to do。😡，So for example， if you say Cha vector 23。

 you basically ask the operating system to get a character from the keyboard right or if you use Tra 21。

 you ask the operating system to output a character to the monitor if you use Cha 25 you ask the operating system I'm done with the program how the program finished the program basically so we're not going to go into how this is implemented it if you're really interested you should really read the appropriate chapter input output for example from Pat Patel but we don't have time in this semester to really go into it in systems programming you will go into it more but maybe in another version of the course we can go into it but not just not this version so this is the program that we wrote and this also in your Pat Patel book that basically implements the construct that we showed earlier that basically implements this flow chart。

And again， I'm not going to go through this in detail。

 you can convince yourself that the program does what it does。

 but again we don't have time to go through that detail。

 you can see that we use conditional bench instructions to create loops and if statements。

 and you can do reverse engineering to identify conditional constructs and iterative constructs like what I show you over here。

 but again we don't have time to go through this in detail。😊，Again， again， nothing is hard over here。

 it's just translating the program into assembly language and then the machine code later on。

 you can also start on the machine code and reverse engineer the program as well right？😡。

And you can see that there's a starting address of the file over here。

 so file actually is stored in memory in this case it's a memory mapped file but again we're not going to go into that in this course so let's talk about debugging becauses going to be something important that you do in all your programming including your very log programming and this is the process of removing errors and programs it consists of tracing the program keeping track of the sequence of instructions that have been executed and the results produced by each instruction and it's clearly a useful technique right and one way of making it even more useful is to partition the program into parts like modules and examine the results computed each module separately。

😊，So high levelvel language debuggers can help you clearly there are many。

 many examples of this that I'm not going to go into make you code debugging provides you elementary interactive debugging operations so let's say look at interactive debugging operations when debugging interactively it's really important for you to be able to put some values into memory and registers you're at the very low level as an assembly programmer right you need to be able to test the execution of a part of a program in isolation maybe one instruction right。

😡，Execute instruction sequence in a program by using the run command so if you have a debugger that supports this。

 you can run instruction by instruction right and run command executes until halt instruction or until a break point so you can step and command basically you can execute a fixed number of instructions you can step one for example you could be to execute every instruction one by one examine the results and see what you if you expect is in the registers and memory and you can stop the execution when desired in debugging clearly you can do that by setting a breakpoint command by stopping execution at a specific instruction you set a break point in a particular point where you want to examine the memory and register values and after this you can examine what's the memory and registers at any point in the program if you have this infrastructure that way you can step through the program so this is very useful clearly and doing this in very log is also very useful except very log is very inherently parallel As because of the Neman model we execute one instruction at a time right so you can actually say I'm going to。

to execute one instruction at a time。And then you can see what the result of that instruction is and if what you expect at the high level as a programmer is satisfied so for example we have a multiply operation in LC3 a program is necessary to multiply since LT3 does not have a multiply instruction and the following program multiplies values r R4 and R5 basically and again initially R4 is 10 R5 is3 I'm not going to go through it in detail but the program produces 40 the question is what went wrong and you can examine it by yourself and to do so it's useful to annotate each instruction so again if you're given the machine code you can easily annotate these instructions and say these are the instructions that I have。

😊，And if we examine the instruction and the contents of the registers after the execution of each instruction。

😊，You may find out that the correct result is here after three iterations。

 but after some point branch is taken and the branch should not be taken if r5 is equal to zero because then you would be multiplying things by more than once so if you go over here R4 is 10 r5 is3 and the program produces 40 clearly program should produce 30 the program iterated once more in the loop basically one too many times because the branch condition codes were set wrong the conditional branch should only be taken if r5 is positive so basically we did a mistake over here in the program we set the Z bit whereas we shouldn't be setting the Z bit we should not be checking the zero condition over here because that is a boundary condition in which the program leads to one more iteration which it should not execute right so the correct instruction should have in VRP。

It is opposed to be RZP。So you can actually find the probe problems by executing the。

Debugugging the program by executing instruction by instruction clearly or by setting breakpoint I'm not going to go into the details clearly so you can do easier debugging with breakpoint as we said previously we examine the instruction instruction by instruction but you can actually set a breakpoint at the branch and see where the branch goes and you can examine the results of each duration of the loop as opposed to examine the results of every single instruction in the loop。

😡，And this way， you can actually look at interesting things that you care about。

 and you can still find the problem basically。😡，Okay so does this program work if the initial value of r5 is0 is another question and let you answer that basically that's another corner case basically if r5 starts with zero。

 does this program still work and the answer is no this program doesn't work basically that's a problem so basically you should test the condition you should test whether r5 is zero first to really understand whether this program to really make this program work so there are multiple boundary conditions that this programr was not careful in dealing with one boundary condition was what the result。

😡，Should have been and what the result So I think I see a question why doesn't it work if55 is equal to zero because you can see that you basically do the addition first right you add r2 to r4 and then you r 5 becomes minus1 over here。

 So remember the value of r5 is。😊。

![](img/aa16fcc74ce514f2dd52a38c336477a5_5.png)

Yeah， basically you add r4 to itself， basically you get the result 10， if our5 is0。

 which you should not get， you should really get zero because you didn't check the boundary condition at the beginning。

😡，Okay， okay， so we discussed the breakpoint so I went to forward okay so basically a good test should consider the coron cases meaning unusual values that the programmer might fail to consider and again this is not a well written program because it didn't consider many corner cases including whether our five was zero and whether when when you should really branch over here。

😊，Okay so very quickly let's talk about conditional statements and loops and MIPS assembly because it's going to be useful in your labs again。

 if you have to go somewhere feel free to drop off。

 you can watch this later or we will learn this anyway in your labs by yourself but I'm going to cover it relatively quickly so that at least if you want to watch it you can actually watch it if you cannot attend it right now but again you're going to do this in your labs as I said so you're going to learn it by hand anyway and the best way of learning is really by handone learning so in MIPS we can create conditional constructs with conditional branches as we discussed you can do branch if equal as we discussed and we're going to see an example of branch of equal so high levelvel code looks like this if I is equal to J F becomes G plus H and then independently of that we subtract I from this is what the program looks like you could call this silly function again and MIPS assembly looks like this basically。

😊，One way of doing this encoting this synmpsses or programming the synmsis basically we branched not equal。

😡，If S4 S4 and S3， basically we check if S3 and S4 are not equal and assume that S3 and S4 contain INJ。

😊，And if they're not equal， we skipped yet。😡，That's what this instruction says right， we go to L1。

 which is the label of the next instruction。😡，So if S3 and S3 S4 are not equal， branch not equal。

 then go to L1。😡，If they're equal that means that we're going to do the act。

 so this is what it is basically it's very simple you compare to two values and you do branch if the two values are different。

😡，So if if the statement was a little bit different。

 you had an if and L statement now you need to do something a little bit more right basically use an unconditional branch to skip the else subtask if the if subtask is the correct one so what does this mean basically it means this。

😡，IfWe write the code like this， this is the corresponding Mips assembly code to the high level code。

 we again have the branch not equal。😊，If S3 is not equal to test4 meaning I is not equal to J。

 we skip ya and we go to done essentially sorry in this case we do the else right yeah that's a different code so we basically need to do the else。

😊，Which is the L1 over here， because if I is not equal to J， we do f equals f or minus I。

 which is implemented by the subject instruction。😡，But if this branch conditions not true。

 we do the ad。😡，But we should not do the else。😡，To be able to enable that。

 we have an unconditional jump。😡，Basically if we do the ad we should really jump to done and skip the subjecttract so hopefully that's clear to be able to implement if an else statement you need two branches one is a conditional branch and the other is an unconditional jump that skips the else part right conditional branch skips essentially the targets that is supposed to be executed if the condition is true and unconditional jump skips the part that is executed the sub subtest that is supposed to be executed if the condition is false there's a question can you jump back in the code absolutely you can jump anywhere basically you can have a label over here saying for example at the beginning of an earlier loop you can have a label at the top for example and you jump to that so you can jump anywhere as long as your offsets are fine basically as long as you don't violate the offsets but even then you need to use a different addressing mode if you want to jump anywhere in the code right。

😡，Okay， so basically I already said this， you compare the two values and if they're different jump to L1 otherwise to execute the L sub task over here right and this unconditional jump jumps to done after executing the if sub task。

😊，Okay while loop is a little bit more complicated as in LCc3。

 the conditional branch checks the condition and the unconditioned branch jumps to the beginning of the loop over here we've seen it in LCC3 now we're going to see it in MIps it's going to be very similar basically you initialize the power and x value so here this loop determines the power of2 equal to 128 which is a very simple calculation as you can see and initially power is set 1 x is set to0 so you need to set those values plus the 128 to compare to and while loop basically does a branch equal over here it has a conditional branch to check if the condition is still whole so you need to check the condition first before entering the loop otherwise you may execute the loop one too many times as we show earlier in the buggy multiplication example here it's not multiplication but it's really figuring out the power raised to the two power of two so basically that's what the branch equal does and then there conditional branch to the beginning of the loop。

😊，Seccutute the loop once。And then。😊，Unconditional bench。

 and then we check the loop exit condition again， whether the power is not equal to 128。

 So if the power is equal to 128， then we are done if the power is not equal to 128。

 we execute the iteration of the loop， multiply power by two increment x by 1 and then go to the beginning of the loop and then check if power is equal to 128 again and you keep doing this until power is equal to 128。

😡，Okay。The implementation of the for loop is very similar to the wire loop essentially this is another loop that is different。

 it's a for loop you can see that you're adding integers from0 to 10 10 is not included over here and essentially it looks very similar right basically you set the variable some I and also you set something to 10 so that you can compare I to 10 at the beginning if I is equal to 10 you jump out of the loop if I is not equal to 10。

 you execute the loop iteration and then you have an unconditional jump back to the branch equal right essentially the same thing basically very similar to the while loop that we saw early。

😊，Okay so you could use a for loop by using the set less than which is a way of setting the registers This is like condition codes in a little bit。

 but you set a general purpose register， not a condition code so if we use the set less than for the less than comparison so let's take a look at this this is another trick you can use for example so basically you again add the powers of2 from one to 100 thiss another loop that does that particular task and to be able to do that you initialize sum and I and then until I is less than 101 you basically find the powers of2 and like this and then add it to the sum and to be able to do that you have some initialization and then you do the set less than basically this what this set less than does this okay I already said this set less than is essentially the statement if the value register s0 is less than the value and register t0。

😊，The destination register gets one， otherwise it gets you。😡，Okay。

 so it's basically this statement implemented with one instruction right it looks nice basically it's a very high level statement。

 if you will， you can directly implement a high level language statement that looks like this。😊。

And then basically it basically tests the condition and sets it less than。

 and then you check whether t1 is equal to0 if t1 is equal to zero。😊，Then basically。

 that means that you need to exit the loop right。😡。

If not equal to zero then you can you should stay in the loop and do the loop iteration and then basically check the condition again and again。

 but you should also execute the set less than an BQ in this case you set less than a register and then check whether that register is equal to zero or one to implement a looping mechanism right another way of implementing it you you could have done in some other way also clearly so here we have shift that logical this is essentially multiplication by two right multiplying by two is the same as shifting left logical in binary by one and we don't use a multiply over here because shift the logical is much simpler and faster in hardware。

WellLet's go into a little bit more into MIPS again this is going to be very simple to many people who know programming so you don't really need to study this if you will。

 but it's instructive I think to look at how the arrays are implemented in MIPS accessing an array requires loading the base address into a register as we have seen earlier so in memory the array looks like this basically you have a base register that is points to the beginning of the array and then each array element is a word in this particular case and then basically each word is in the next word location。

😊，Which is has this address， as you can see over here on the left。So in MIPS。

 this is something we cannot do with a single immediate operation loading the base register。

 so what do we do？😡，We use what we learned earlier load upper immediate plus or immediate right L Ui and orI we've seen this before。

 if you want to load this address that we know into a register， let's say SEO。

 we first load the upper immediate。😡，One， two， three。

 four to the top 16 bits of the S register and then or。😡。

They register with the 16 bits coming from this immediate value 8000 over here and then you now you have this address。

 the space address of array in Se so now you can see how we can construct an address。

 this is very similar to LEA load effective address in LC3 except it's more powerful because now we can load a 32 bit value over here。

😡，So let's take a look at how we manipulate arrays basically if you want to manipulate an array we first load the base address of the array into register using LUi and OrI。

 as you can see over here， we're going to assume that that's the base address of the array now the base address of the array is in S0 and we're going to use things that we have seen earlier basically so if you want to get the element0。

 we calculate the address as base address plus offset0 if you want to load element1。

 we calculate the address as base address plus1 times four bytes per vert。😊。

That's why this offset is four， and then you can actually do the multiplication， do the store。

 and then do the multiplication and the store the multiplication again is shift left logical because that's simpler to do than just a multiply operation。

😡，Now let's talk about function code and this is the last thing that I'm going to talk about and conventions。

 it's going to be interesting because assembly is interesting I think here。

 but clearly we want functions or procedures or modules in a programming language because this enables us to reuse code and we have frequently access code it makes a program a more modular and readable and functions have arguments and return value or values so this is one example right you have a main function over here that gets executed and then you have a some function that gets called that essentially returns to sum of the two parameters。

 two arguments that it's given。😊，So let's define something so calling function is called the color。

 so the main function is the color over here and the called function in this so vein as I said。

 called function is called the callli so sum function is the call over here。😡，Okay。

 so there are a bunch of conventions that people provide when you do assembly programming so that you don't destroy registers unnecessarily and so that you can actually have much more modular code if you obey these conventions。

😡，This is also called the programming interface or essentially a programming interface to the assembly language for a given architecture。

 if you follow these conventions and if everybody follows these conventions。

 you don't need to save or restore some registers as we will see。😡。

So basically caller passes arguments， jumps to call E。

 call E performs the procedure and returns the result to colorer。😡。

So that's and then returns to the point of the call basically let's take a look at this。

 but callee must not overwrite registers or memory needed by the call and this is really important if the callee overwrite some registers or memory needed by the call when you return back to the color too bad you don't have the registers you need you don't have the memory you need so that's why we need conventions basically so there are some convention nips and LC3 and again these are conventions that you should obey if you want to actually be compatible with the rest of the world。

😡，So in MIPS you can call a function or call a procedure using the jump and link instruction in LC3。

 you can use a jump to subroutine JSR and JSR these are different ways of calculating subroutine address basically。

😡，Or you can return and you can return from procedure and MIPS using the jump register instruction in LCC3。

 you can return from subroutine re instruction over here。😡。

And the argument values are supposed to be stored in MIPS in registers a0 through A3 and the return value in MIPS is supposed to be stored in v0 okay so that's expectation and v0 is mapped to some register as we have seen earlier that I don't have over here again。

😡，So basically let's take a look at a simple example， this is our high level code。

 the main function calls a simple function that just returns and you have this in main function。😊。

So the MIPS assembly looks like this， so what this does is basically you have a jump and link。😡。

To simple and then you have the ad in the next instruction so a simple in this case doesn't contain anything。

 doesn't do anything except it returns back right to return back you just to use the jump register register a so why register a。

😊，Because jump and link for a special instruction， jump and link jumps to simple and saves PC plus4 in the return address register。

 which is a special register in the general purpose register file RA。😡，In assembly。

 you can assume that after you do a jump and link， the return address， meaning。😡。

The instruction after jump and Li will be stored in RA。😡，In的。Call he， okay？So basically。

 that's why you can do jump register RA and then go back to。😡。

This ad instruction that comes right after jump and linked。😡。

Hopefully that makes sense right this makes life easier in programming basically now you have programming support。

 the hardware support or hardware software interface support for function calls in the instructions at architecture。

 right？😡，In LCC3 you have a similar thing basically you have JSR or JSRR that puts the return address in R7 so there's a specific register RA also has a number actually。

 but basically R7 is the RA in LC3， but it's essentially the same thing。😡，呃。Okay。

 so there's a very good question。 What happens if we call a function from within a function。

 Don't we overwrite R then absolutely and then。😡，If you do that。

 the task of the simple function over here， if it calls another function。

 it has to save RA at that point basically， and that's why we're going to introduce the concept of stack for example。

 in a little bit。😡，So that's a very good question， basically because somebody needs to say if you're going to overwrite a register that you're going to need later or somebody's going to need later。

 you have to save it in memory and then reload it before it needs to be used。😡，Okay。

 basically as I said， jump register RA jumps to address in RA， LC3 simply uses the RE instruction。

 which is essentially a jump register， but it's a specialized jump register which basically sets the PC to RA essentially。

😡，Okay so let's take a look at the high level code over here。

 let's look at a little bit more complicated example。

 so here were we're looking at a main that's called di of sums it does something don't worry about it but you can you can see what it does basically it has f plus g and subtracts it from a plus I and then it basically returns the result right so now this is a little more sophisticated function。

😡，So what does the main do basically main sets up the arguments。

 so remember this is the convention a0 a1， a2 a3。😡。

Basically it can pass four arguments to the function and then it sets two， three， four， five。

 those arguments， two， and then it does jump and link to diff of sums。😡，And then di of sums。

Read the arguments， assume that the arguments are in a0 A1 A283。

 so there's some convention for sure that you need to obey to make this work。😡，え。And then。

It subtract， add add Subtract， and then puts the result into v0。😡，And。Jump register RA。

 which goes back over here and then main takes the result and V0 does whatever it needs to do with it basically to S0 Okay。

 so basically we used the convention arguments are stored in a03 a3 and the return value stored in V0。

😡，Okay， I already said this basically。And the return address is stored in RA again okay so there is an need for stack for function calls for the reason that we just discussed actually based on the question that I received。

 so if you look over here the diff of sums looks like this right t0 t1 s0 but if the main function was using some of those registers that was used by the di of sums right t0 t1 s0。

😡，Well too bad you're overr them right so if you remember over here we are using T0 T1 SEO。😡。

And we didn't think about this right if the main function was using T0， t1 and a0。

 if of sum is overwriting them。😡，And but we can fix this problem by using a stack to temporarily store the registers that we're overwriting and then we store them back after we're done with the function。

😡，So the concept of a stack is basically it's a memory area that's used to save local variables that we operate on temporarily it's a last in first out queue you may have seen this in other programming language courses the stack pointer it a special register actually points to the top of the stack it goes down in MIPS it's a convention again all of these things are conventions even the naming is convention right so it looks like this basically so it can push values on the stack and you can pop values out of stack so look over here if you look over here this stack pointer points to this location this address it has this value maybe you can push two registers on the stack here that have two values AABB CCDD and 11223344 now you added or push two values onto the stack and when you actually start before you start the function called you actually say oh okay I'm going to save the temporary registers that I'm going to work on。

😡，Just to make sure that no one is going to I don't actually overwrite the calling functions registers right and you can push them on the stack and at the end of your function。

 you can pop them from the stack and put them back into the registers that where they were supposed to be。

😡，So here two words are pushed on the stack， let's take a look at this example。

 so we have the same function that we saw earlier it's writing T0 t1 SCO but we don't know if the calling function uses them。

 so what we do is basically allocate space on the stack to store three registers basically we do this to the stack pointer and then we basically store S0 t0 and T1 to memory locations on the stack。

😡，And now we can overwrite because we store the old values of S0 or t0 and t1。

 now we can comfortably overwrite t0 or t1 S0。😡，And then compute value is based on that based on whatever you want to do。

😡，And at the end， before we do the jump register， register A。

 we load back the values that we pushed on the stack into T1。

 Tser and Se to the corresponding register， so this is called spilling values on the stack and filling values back from the stack we're spilling values on the stack because we're using some registers that we don't know if somebody else used that called us。

😡，And then before the function returns， we're going to fill the values back into the register so that the calling function sees the registers as they sent the register file to us okay that's the idea over here and then we delocate the stack base because the stack pointer can also be used by the calling function basically right so stack pointer is a stack is a common memory area that's used by all functions and this is a very general way of saving and restoring registers as you can see so the question that was asked earlier RA right register a if you're going to overwrite if you're going to call another function inside diiff of sum so if you're going to call for example another function。

 you'd better save RA on the stack。😡，And get back RA after that from the stack when you do that。

Again， saving and destroying all registers requires a lot of effort in MIPS there's a convention about temporary registers。

 so actually we did not need to save temporary registers assuming everybody will be mentioned again。

 there' is no need to save the temporary registers because the convention says temporary registers。😡。

The calling function should not expect the values and temporary registers to remain the same after it calls a function。

 okay that's a convention again， these are programming conventions。😡，Okay。

 so there's a register saving convention that enables us to use temporary registers without worrying about the calling function。

 but if we're using a0，😡，We'd better save it because SR doesn't isn't that part the part of that commission basically temporary registers are called non preserved registers。

 they are not saved thus they can be overwritten by the function the function is not the function's responsibility to save them essential。

😡，AndBut registers as zero and a7 are preserved it's or they're called calla which means that it's the functions responsibility to save them going to overwrite them that's true for RA as well by the way okay okay so now we're done actually we covered a lot of interesting concepts again you're going to learn this anyway at some point but hopefully it's interesting if you state if you didn't stay that's fine you can watch it or if you really need it you can actually refer to the lectures when you need it from the labs but essentially we've covered all these concepts relatively quickly。

😡。

![](img/aa16fcc74ce514f2dd52a38c336477a5_7.png)

![](img/aa16fcc74ce514f2dd52a38c336477a5_8.png)