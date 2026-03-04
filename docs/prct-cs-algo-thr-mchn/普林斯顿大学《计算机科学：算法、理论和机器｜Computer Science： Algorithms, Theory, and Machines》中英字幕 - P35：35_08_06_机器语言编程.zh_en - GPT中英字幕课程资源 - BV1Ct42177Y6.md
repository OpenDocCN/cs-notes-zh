# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P35：35_08_06_机器语言编程.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/10f9f012a46fd17171e27948727f87b0_0.png)

Next， I want to convince you that really you can do much more than just adding two numbers。

 even with toy and with switches and lights。So the basic concept is that even the few instructions that we've given for Toy support the same basic programming constructs that Java does so we have primitive data types we've got the arithmetic operations and we've got the bitwise operations we have things like assignment statements and some math loading stuff into registers and implementing things。

 we have conditionals and loops and we'll talk about that， we can do arrays。

 that's what opt codes A and B or four， we'll talk about that in the next lecture。

We're going to talk about standard input and output in just a minute and we have advanced programming constructs as well。

 we can do functions in libraries， that's what Opcodes E andF are about and there's plenty of discussion in the text and the book site about that。

 we're not taking the time to do it in lecture。And link structures as well， in fact。

 in the book there's the toy program that uses binary search trees to deduop an input that with no limit on its length。

 it's kind of amazing that you might think that you can perform these kinds of functions with the very few instructions that we have but actually if you take the time to do it you'll see that really the toy program for binary search trees is in some ways easier to understand than the Java program and lots of these things are done with toy programs that only use 10 to 20 or 30 instructions。

 not very many instructions at all to do really a lot it's really quite amazing and it's worthwhile to take the time to look at machine language programs that do familiar tasks and there's plenty of examples of this in the book site and on the book site in the book。

So let's look at conditionals and loops to start。So。There's instructions。

 a few instructions within toy that change the value of the PC。

 and that's how we control the flow of instruction execution。

 we test a register's value and change the PC depending on the value。

 so that's up code C and up code D， branch of zero in branch of positive。呃。

So these instructions take a register and an address and they test that register and depending on the result。

 they change the PC to that address， so just a really simple program that computes the absolute value of the number in register A。

DA12， so D's Opcode branch of positive， check if A is positive， if it's positive。

 then set the PC to memory location 12 this instruction is at 10， the next instruction is 11。

 and then so 12 would be skipping the next instruction。And what's the next instruction。

 it's Op code 2， which is subtract and the opera ends are0， which is0 by convention and register A。

 so it subtracts register A from zero。So if it was negative。

 that'll make it positive and then puts the result into Reg A。

 so that's a two instruction program that computes the absolute value。

So that's a conditional and a typical loop works as follows assume let's assume that Reg 1 has the value1 in it the up code C is branch of 0。

 and then we test the value of register A if if it's zero we go to 15 that's branching out of the loop。

 then we have whatever a loop instructions might be and then we have somewhere a subtract instruction which says2 is subtract。

 one has the value 001 a is got some value， subtract1 from it and put the result back in a that's decrementing register a by1。

 and then after you do that do a branch if zero on register zero which always succeeds and sets the PC to 10 so you can see that's how we can implement while loop that decrements register until zero。

Just those few instructions， we can go ahead and implement the kinds of constructs that we use all the time in higher level languages like Java。

And we'll give an example of a program that does this in just a minute。

 so that's the kind of Java issue expression of this same code and we'll try to document our programs like that without being too personnicty about the correspondence。

And as we saw when we first programmed in the second lecture once we got to loops。

 we realized that all of a sudden that gives us the capability to do way， way。

 way more than we could do without being able to control the flow。

 but it doesn't take much just a couple of toy instructions to get us there。

But the other thing as input and output， it's one thing to implement a program with switches and lights。

 but to implement to input data with switches and lights people knew right away is just not going to work so one of the very first things that happened on all the earliest computers was to have some way to get data from the outside world into the machine and just to give an idea we're going to talk about paper tape and that's actually the method that I used for a couple of years and what they literally did was on the side of the machine they bolted some IO devices that could read and write paper tape and we're going to talk about them in terms of standard in and standard out that are familiar to you and what is paper tape it would come in rolls or sometimes what would come in what's called fanfolded to be folded。

And it's a paper and it we think of it as unbounded in length you could read as much as you want。

 and it's got holes punched in it， we encode our 16 bit words in two rows on the tape。

 so this is a 16 bit word where the first8 bits or0， then 0011 and then 0111。

 and then there's little holes in the middle there are sprockets that are used to drive the tape through the tape reader。

So to write a word， there's a little thing that can punch the holes and it would just punch a hole corresponding to each one。

And to read a word， basically the device would shine a light behind the tape。

 and then on the other side it would sense the holes and then it would know what's supposed to be zero。

 what's supposed to be1。And that's it very simple device and how do we access this with a toy program Well what we're going to do is just connect this thing to memory location FF and so memory location FF is not really a memory location if you store something to memory location FF instead of storing that in the memory it would activate the paper tape punch to punch the holes corresponding to the values of the word that you said you'd store and to read you'd do the same thing when you load from FF then the device that would be a signal to the device to go ahead and read a word and provide that put that as if it was came from memory。

Very simple device。 And actually， the。Paper tape hardware itself is not really significant because very quickly that was replaced by magnetic tape which could hold way way more data and go a lot faster。

 but from the point of view of the program is no change at all It's like standard input and standard output I think of the input stream and the output stream is infinite within my program I don't have any bound I just write to FF or I just read from FF so that changes quite a bit what we can do with toy programs and we'll talk about the impact of this in the next lecture but just as an example let's look at flow this is a real program that illustrates the flow of control and standard output So what this program does is print on paper tape the Fibonacci numbers and it's kind of a toy example。

 although I have to say with early computers。YouHave to imagine doing this stuff with pencil and paper。

In the excitement of being able to actually compute things that you didn't know。

 like really large Fibonacci numbers or other basic mathematical properties of integers。

 people were very excited to write programs like this and be able to learn things really about math。

And so lots of the early programs were of this form。But if you want。

 you can think well this is scientific data of some kind that is going on to the paper tape fertilator processing and certainly there was quite a bit of that as well。

 but let's look at the example just I think you'll see after this example there's lots of things you could do with with this computer this is just a 13 13 instruction to get this job done so let's look at what it does so our convention is to put the value one in register1 and that I talked about instruction 7 that's load address instruction and what that does is take the value of the address and put it in the register and then clear out the upper bits of the register with zero so that's a quick way to get a value into a register。

And then we start out with register A and register B， and we set them to one。

And then register9 is going to get the location of whatever is in memory location of 4 C。

 if you look down at 4 C， it's got the value A， so that's data for this program it says we want to punch out 10 Fibonacci numbers and we're just putting 10 for this example。

 we could put of course， a much larger number if we want it。

So that's going to be our counter for our loop， that's n and register9 is our index for our loop。

 or that corresponds to I in the pseudocode right。So now we test if I is 0 or register 9 is0 and this is our while loop construct C means branches 0。

9 means register 9 and then 4b is down at the halt instruction so this is going to be our loop it's not zero of course and on now it says just right register A to standard out that's just 9 AFF and we execute that。

We punch out of one now Fibonacci numbers， so it's A and B of the two previous。

 so we add them put the result in C。And then move B to A and C to B。

 those are going to be our two previous that we'll always keep track of。

And then decrement register nine。啊。And now we'll just show what happens every time through the loop we go on and decrement register 9 and seize the some of the two previous。

 and then we update the two previous。So a very simple program and again we could make that 100 or 1000 or all the way up to 32。

000 things that we could punch out and it could be a much more complicated number than the Fibonacs。

And then finally， we come to the halt instruction。So with that sample program and this slide。

 which is called the Toy Ref card， you can already， I'm sure， imagine writing code to solve many。

 many of the computational problems that we addressed early on in Java。

If it involves S of control and it follows integer bitwise operations。

 there's really a lot you can do， you'll find plenty of examples in the book。

And the other thing to remember about this card is that it is a complete specification of what happens in a computer。

 any 16 bit of value can be decoded using this card and the pseudocode in blue on the right specifies exactly what toy will do if you get that instruction。

We'll describe a few more in the next lecture and they're all described with examples on the book site and in the book。

 but this is a complete description of what goes on in toy。

 and real computers for many years had programmers carried these cards in their pocket as a full description of what you needed to know while programming。

Sometimes the cards got really quite detailed， there were computers that had 256 instructions so the card folded and there was lots and lots of information on it。

 but that's something that every programmer had to know and had to have quick reference to when they looked at what's in the memory。

 they had to know exactly what the computer would do if it happened to interpret that thing as an instruction。

 or when you're crafting a program， this is what you have to work with， it's your manual。

So toy programming is an interesting intellectual challenge and I encourage everybody to learn more about it。

And so the kind of thing though that you have to know to be sure that you really understand what's going on。

 you have to be able to answer questions of this sort， so I give you a 16 bit number。

 what is that number if it's interpreted as a toy instruction or as a twos complement integer value for all different kinds of numbers。

Well， 1 a75 that's easy， one is add instruction A is the result， we're going to add register 7 and5。

 put the result in A。Twos complement integer value。 Well it's a1。 it's positive。

 so we can use hex to do it with one times 16 Q plus 10 times 16 squared plus 7 times 16 plus5。

And actually， this kind of conversion is an easy programming exercise and in the book and in the book so you can see a general purpose program for doing these kinds of conversions where you could write a toy program to do it even So what about zero FFF well the card says if the initial four bits or zero。

 that's a halt instruction and that's it rest of it's ignored。What about it's a twos complement well。

 it's easy way to compute that is if you have 1000， that's 16 cubed and subtract1。

 16 cubes 4096 to subtract one and get 4095。8888， well 8 is load instruction。

 next state means register8 and 88 means memory location 88 and as the twos complement an integer value。

 well you can do it by converting to binary and so forth and converting back。

 but actually the idea of flipping all the bits and adding one works in any number system and so actually you get this by subtracting all from 15 and then adding one one less than the base。

So these types of questions， a short answer question that you might find in a quiz or exam on this material。

 you want to be able to know what every 16 bit value means as a toy instruction or as a data value so just as a trick how do you flip all the bits in a toy register well if you X or with all one then X or with one flips bits and that's a kind of programming trick that every programmer knows。

 everybody who programs at this level knows。And then you should be able to figure out what small programs do。

 and that might seem amazing to you， but this programming model is really simple。

 it's much simpler than Java and it won't take you long to figure out just by studying this program just by the examples that we've seen that what this thing does is go through a loop 10 times doubling the value in Reg 2 and that' so it computes 1024。

So that's another type of question that anybody can answer after seeing this lecture。

So how does toy really relate to your actual computer， they're totally different computing machines。

 but they both implement basic data types， conditionals， loops， and other low level constructs。

They both can to have functions， arrays and other high level constructs。

 they both have infinite input and output streams， really the whole programming model that we talked about for Java toy implements just as well as your laptop does。

You might say， well， but 256 words is that really enough to do anything useful at all。

 it's such a small computer and again we keep keep it small to keep the scope small that you can understand what goes on inside the computer and actually will'll talk next time that absolutely 256 words is enough。

 In fact， all our sample programs of the books which cover a big range all fit in the same memory and we'll talk more about this next time then if you've seen theuring the theory lectures or when you see the Turing lectures。

 you know that actually if you just change the IO device to both read and write。

 which you can do nothing about the machine that says that then toy becomes a touring machine it means you can compute anything that any computer can compute。

So toy is in a very strong sense equivalent to your laptop and really all the computers that have been developed in the last 50 years have all of these same characteristics。

 it's really really quite an amazing phenomenon。Now， yes。

 we want a faster one and we want more memory when we can afford it and that's another aspect of the history of computing is that that's always true。

 you want a faster laptop with more memory people wanted that with toy in the last 50 years have been a continuous development of providing that。

 but what the computer does basically not much change。

 That's what we're going to look at more next time。



![](img/10f9f012a46fd17171e27948727f87b0_2.png)

![](img/10f9f012a46fd17171e27948727f87b0_3.png)