# CoreDumped【中英⚡图解计算机体系结构｜Computer architecture from scratch】 p05 P5 How computer processors run conditions and loops -BV1mBWzzAEek_p5-

This video was sponsored by Brilliant。To run programs， computers follow instructions step by step。

 but that doesn't mean they always execute instructions in a strict sequence。To be useful。

 computers must be able to make decisions and repeat steps。In today's episode。

 we'll explore how computers handle conditions and loops。Hi friends。

 my name is George and this is Core Dumped。Before starting。

 a quick reminder you can find me on social media。Let's start with a quick recap of how CPUs run instructions When we write programs we typically use programming languages that computers cannot understand this is why compilers exist a compiler is a program that takes code written in a programming language and translates it into something else。

 usually an executable file。It is a common misconception that an executable file is just a list of CPU instructions。

But it also contains the data that our program needs to accomplish its purpose。

Consider the example shown on the screen。Here， the numbers 20 and 100 are values that our program will need at runtime。

 so the compiler must include those values somewhere in the executable file。To run the program。

 its executable file is loaded into memory， allowing the CPU to begin fetching instructions from it。

Remember， a processor is connected to RAM from which it can read and write all sorts of information。

 including both instructions and data。Running an instruction involves passing through three stages。

First， the CPU needs to read the instruction from memory to do this。

 the content of the address register， sometimes called the program counter。

 is sent to the memory's address input while the Read enable signal is activated。

This causes the memory to output the content at that location。

 which is then written into the instruction register of the CPU。

This stage is known as the Fech stage。Next， the control unit reads the content in the instruction register to interpret the instruction。

 or in other words， to determine what action the CPU should take next。

This is known as the decocode stage， and once the instruction is decoded。

 the control unit sets everything up so that the instruction can be executed in this example it loads the content from memory location 5。

 which is the number 20 into register zero。This is known as the execute stage。Finally。

 after the instruction has been executed， the control unit increments the value in the address register。

This is done to ensure that when the CPU returns to the fetch stage。

 it will retrieve the instruction immediately following the one just executed。

Our example program requires four different instructions， like the first instruction。

 the second one also retrieves a value from memory into the CPUU this time from memory location 6 into Reg 1 again。

 right after executing the instruction， the value in the address register is incremented。

The third instruction is fetched， but this time it's an arithmetic operation decoding this instruction tells the CPU to add whatever values are currently held in register0 and register 1。

 and then write the result back in the register that contained the first opera end。And again。

 the program counter is incremented。Note something important。

The ad instruction wouldn't make sense without first loading into the registers the values we want to add。

In our example program， we don't just want to add two numbers。

 we also want to store the result in a variable。When we assign values to variables。

 it's because we want to access those values later using the variable name， in other words。

 to remember the value。Translated into low level terms。

 this means the result must be stored in memory so that we can retrieve it later if needed。

That's exactly what the following instruction does。

The store instruction directs the register to send its value to memory， specifies an address。

 and activates the right enable signal， This tells the memory that we want to write a value to that location instead of reading from it。

 and just like that， our result is now safely stored in memory location 7 At this point our program should be complete。

However， the CPU itself cannot differentiate between instructions and data to prevent it from mistakenly fetching data as if it were more instructions to execute。

 a special instruction is added at the end。This instruction tells the CPU to halt。

 ensuring it doesn't continue running unnecessary operations。

Now let's modify our program by adding a new line of code。

The instructions for the first line remain almost the same， except for the addresses。

 I'll explain this further in a moment。The second line also involves an addition。

 so the opera need to be loaded into registers； the first opera is the value of the variable A。

 the second opera should be the number1， then the addition is performed and the result is saved while this approach is valid。

 we can optimize it。

![](img/323e4c9fe58ac974d61072f038cb9b3d_1.png)

But first， a quick message from Brilliant On this channel， we love learning in an intuitive way。

 rather than endlessly reading PDFs that's why Bri is designed for you。

Brilliant is a learning platform designed to be uniquely effective。

 their first principles approach helps you build understanding from the ground up。

Each lesson is filled with hands-on problem solving that lets you actively engage with concepts so you can learn by doing rather than just reading Brilliant helps build your critical thinking skills through problem solving。

 not memorizing， and remember， being a good problem solver is what differentiate good from average programmers。

You can start your learning journey with courses like thinking and code， creative coding。

 programming and Python， and even more advanced topics like how LLMs work you can get a 30 days free trial of brilliant premium and get a 20% discount on your annual subscription if you sign up using the link in the description below。



![](img/323e4c9fe58ac974d61072f038cb9b3d_3.png)

![](img/323e4c9fe58ac974d61072f038cb9b3d_4.png)

![](img/323e4c9fe58ac974d61072f038cb9b3d_5.png)

First， we could use a special instruction from our architecture that allows us to increment the value in a register without loading the number one into another register。

Next remember that the value of the variable A was stored in Reg zero when the previous edition was performed。

 as we haven't loaded anything else into that register since then， the value of A is still there。

 making the load instruction unnecessary。There are all sorts of clever tricks to reduce the number of instructions needed to run a program。

 and compilers do it all the time I'm considering making a video on basic compiler optimizations。

 so make sure to subscribe。Our compiled program would look something like this。

But as I mentioned before， there's a small issue with the addresses。For example。

 the first two load instructions should load data， but since we added more instructions。

 the values 20 and 100 are no longer in the same memory locations as before。

 so we need to ensure that we provide the correct addresses。

The same issue occurs with the store instructions。An old but good trick to simplify this process is to place instructions at the beginning of memory and data at the end。

Given that our architecture is very limited， with only 16 RAM locations available。

 our program will end up looking like this。Modern architectures handle this in different ways。

 but that's not the focus of this video。To run this program。

 we loaded into memory from this point onward， instead of manually animating everything。

 I'll use a small program I coded， this would allow us to visualize data in different formats so it is easier to understand。



![](img/323e4c9fe58ac974d61072f038cb9b3d_7.png)

Just remember that in actual hardware， everything is still ones and zeros。

Running our program will look something like this。This is fundamentally how computers run programs。

 it's all about moving data from memory to the CPU， manipulating it in some way。

 and then storing the result back in memory， executing one instruction after another。



![](img/323e4c9fe58ac974d61072f038cb9b3d_9.png)

This approach makes sense because when we write programs， even in higher level languages。

 we still write them step by step or line by line。But we haven't yet considered conditions and loops。

The ability to do one thing or another， depending on the situation， or to repeat steps。

 is actually more critical than many people realize； in fact， without these features。

 computers would be extremely limited in the tasks they could perform。

We'll discuss Turing completeness in another episode for now。

 let's focus on how computers handle conditions and loops。

We'll start by manually compiling a program， what we have here is an infinite loop。In the first line。

 we initialize a variable with the number0。To do this。

 we need to load the value into a register and then copy it to the memory location where the variable A will reside。

For the line inside the loop， we need to perform an addition。

Since the most current value of the variable A is already loaded in Reg zero。

 we don't have to load it again， so we can immediately use an increment operation to add one to its value。

But we're not just adding， we're also updating the value of variable A with the result of this edition。

 so a store instruction must follow。But we need this process to repeat indefinitely。

 this is where the jump instruction comes into play。As you can see。

 this instruction has a memory address， as its name implies。

 its sole purpose is to make our program jump to that location since it is making the program jump to a previous instruction。

 at some point the program will reach the jump instruction again。 The halt instruction is there。

 of course， but it will never be reached because the jump instruction makes the program return to a previous step。

If you're wondering how this works internally， it's actually very simple。

Jump is just a term referring to the effect of executing this instruction。

 what this instruction really does is tell the control unit to overwrite the content of the address register with the provided value。

So is similar to the load instruction， but we are writing to the address register instead of the general purpose registers。



![](img/323e4c9fe58ac974d61072f038cb9b3d_11.png)

By doing this instead of incrementing the value of the address register。

 the CPU fetches an instruction that is not the next one in sequence。

 which appears to us as if it's jumping。And that's how we implement an infinite loop at the hardware level。

 although this is cool， jump instructions are limited because， well， they always jump。

But what if we need to jump only if certain conditions are met， before answering that。

 I need to talk about flags。

![](img/323e4c9fe58ac974d61072f038cb9b3d_13.png)

Let's run a simple program where we subtract a number from itself。Nothing new here。

 we load the number 12 into a register， subtract this value from itself。

 and then save the result in memory。

![](img/323e4c9fe58ac974d61072f038cb9b3d_15.png)

Now let's run this program。The result is obviously zero。

 but did you notice something What are those little squares anyway。

 Those squares are one bit registers called flags。

![](img/323e4c9fe58ac974d61072f038cb9b3d_17.png)

Every time the ALU performs an operation， it doesn't just output the result。

 it also provides extra information about the result。When any of these flags is set to one。

 the ALU is notifying us that the result of the operation has either overflowed is zero or is negative。

Since the result of our operation was zero， the ALU is notifying us about it。



![](img/323e4c9fe58ac974d61072f038cb9b3d_19.png)

Or for example， if we run the infiniteite loop program。

 we'll notice that when the variable A reaches the value 255。

 incrementing it causes the overflow flag to turn on。



![](img/323e4c9fe58ac974d61072f038cb9b3d_21.png)

For those unfamiliar with these concepts， this happens because the number 256 is represented by a binary sequence that can no longer fit in one bite of information。

Here's another example； if we subtract a larger number from a smaller one。

 the result will be negative， and the negative flag will notify us of that。



![](img/323e4c9fe58ac974d61072f038cb9b3d_23.png)

But why would the ALU highlight these kinds of results， the reason is simple。

 it allows our program to use this information to make decisions。



![](img/323e4c9fe58ac974d61072f038cb9b3d_25.png)

This is where I can finally introduce you to conditional jumps。

The way these instructions work is by jumping to the specified address。

 but only if certain conditions related to the state of the flags are met。

That's the best way I can explain these instructions in general terms。

I suggest taking your time to review this slide， as we'll use these instructions in the following examples。

Let's create a while loop， but this time we'll add a condition so it won't run indefinitely。

Once again we're going to manually compile this program。

 the first line of code involves loading a constant value and storing it in the address where a variable resides。

But this time we can't just start executing the lines inside the loop and then jump back because now we have a condition to check。

Now think about this， whenever we want to compare two numbers。

 what we're really doing is performing a subtraction。

The difference between A and 5 is a third number we'll refer to as B。

There are only three possibilities for this number。If B is negative， it means a is lower than 5。

 if B is0， it means a and 5 are equal。 If B is positive， it means a is greater than 5。

 So if we want to check if a is lower than 5， we can subtract these numbers wheneverever this condition is met。

 the negative flag will turn on allowing us to use a jump negative instruction to detect it。

To implement this in our program， we need to load the number5 into another register and then subtract this value from the value of A。

 which is already loaded in register Ze。Immediately after the subtraction。

 we use a jump negative instruction to check if the result was negative， and if so。

 jump to the part of the code that instructs the CPU to execute the line inside the loop。

And after executing the line of code in the loop， we need a jump instruction to return to the subtraction instruction。

We jump to the subtraction because before each iteration。

 we need to check if the condition is still met。If the subtraction doesn't trigger the negative flag。

 the conditional jump won't occur， and the CPU will execute the instruction immediately following it。

Remember， the flag won't turn on when the loop's condition is no longer met。

 so at this point we can use an unconditional jump to break the loop。

Since there's no more code after the loop， the program should halt here。

If I were to match each line of this code snippet with its respective assembly code。

 it would look something like this。As long as the condition is met。

 the conditional jump and the unconditional jump at location 9 will cause the CPU to execute the content of the loop。

 but once the condition is no longer met， the conditional jump fails。

 allowing the CPU to execute the next instruction， an unconditional jump that sets the program counter out of the loop。



![](img/323e4c9fe58ac974d61072f038cb9b3d_27.png)

Let's run the program。You can see that while the value of the variable A is less than 5。

 these instructions are executed， however since the value of the variable increases with each iteration。

 at some point it will equal 5， causing the subtraction to no longer trigger the negative flag。

 thereby breaking the loop。

![](img/323e4c9fe58ac974d61072f038cb9b3d_29.png)

Now if you are wondering how if statements are processed by CPUUs， I have good news。

 you already know how。In the Wild loop example， we evaluate a condition。If you think about it。

 these two programs are very similar， the only difference is that with the if statement。

 we don't have to go back after executing the code inside the block。

 so the unconditional jump is unnecessary。If the condition is met， the inner block will be executed。

If the condition is not met， the conditional jump will fail。

 and the CPUU will execute the next instruction， effectively skipping the code inside the if statement。

Explain this way， assemblyly is not that difficult， is it？Also。

 the comparison won't always be the same， we might want to use an equal2 comparator。

 which we can detect by checking if the subtraction triggers the zero flag。

 then using the jumpmp Ze instruction。Or if we want to check if a is greater than 5。

 subtracting the two numbers shouldn't trigger neither the zero nor the negative flags。

 something we can detect using the jump above instruction。Before we wrap up。

 here are a few clarifications。The instructions I've been using don't come from any real architecture。

 but from an instruction set I made up for this video。

I tried to use very descriptive instruction names to make it easier for beginners to understand。

 I know dealing with assembly can be challenging， but I've tried my best to make things intuitive and clear。

 I hope you enjoyed this video。 If you learned something， please hit that like button。

 It's free and would really help me a lot。

![](img/323e4c9fe58ac974d61072f038cb9b3d_31.png)

![](img/323e4c9fe58ac974d61072f038cb9b3d_32.png)

Also the tool I use to run these examples is available at this URL you can use it to run the program step by step as slowly or quickly as you want。

 just keep in mind that is not responsive so try to use it on a computer and not on a phone there are more software related videos on the way like CPU scheduling and threading so make sure to subscribe you don't want to miss them see you in the next one。



![](img/323e4c9fe58ac974d61072f038cb9b3d_34.png)

![](img/323e4c9fe58ac974d61072f038cb9b3d_35.png)