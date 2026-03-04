# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P36：36_09_02_视角.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

To really understand toy program， everybody's encouraged to study the book and try some of the exercises and read the programs there。

 We have several toy programs that you can easily learn from。

 and today we'll give a couple more examples of toy programming。

 but really today's lecture is about putting toy in context。

 both in historical context and to consider some of the implications of having a machine that operates with such simple rules。

Let's start by putting Toy a little bit in perspective。So let's consider Toy versus your laptop。

 They're different， totally different computing machines， while one's imaginary。

But they both implement basic data types， conditionals， loops， and other low level constructs。

You can have arrays， functions， library， and other high level constructs。

 and we'll talk about that a little bit today， and both have infinite input and output streams。

So really， what you can see eventually， if you look at this issue enough。

 is that all the basic building blocks that we studied when you first did Java programming。

 it's possible to implement all of them in toy。Now you might say， well， but toy's only got 256 words。

 is that really enough to do anything useful， and it absolutely is。

 we'll talk about that in just a second。Of course， we definitely want a faster version with more memory when we can afford it。

 but the point is that everything that we've done with Java really is possible to do with toy。

 it's just a matter of scale。So let's talk about this issue about 256，16 bit words。

 That'd be 4096 B of memory。 Is that really enough to do anything useful。

So here's an example from an old computer from the 1960s， 50 year old computer。In those days。

 every bit was a physical piece of metal that had three wires running through it。

So1 thousand0 bits was something that was difficult and expensive to produce。

 but this is an actual 1000 bit memory if you had four of those you'd have 4000 bits of memory。

 is that enough to do anything useful well actually it is because this thing is the memory from the Apollo guidance computer that got men to the moon and back。

Here's another example， this is an experimental computer at MIT， it's got more bits， it's got 24。

000 bits， and this was earlier， this was in the late 1950s and people were using computers like this like toy to do biomedical experiments and all sorts of other experimentsation。

This is a gentleman named Wes Clark in the early 1960s， and I put his picture up because his son。

 Doug Clark， is my colleague and has taught this course many times。

So let's look at this even in more detail， so 4000 bits of memory。

 so actually if you consider the contents of the memory registers and PC at a particular time。

 we talked about this at the beginning that provides a complete record of what a program has done and it also completely determines what the machine will do next。

Toys a determining machine based on just these bits of memory。

 and if we count up the total number of bits involved well actually since we use the last location for standard input。

 there's 255 times 16 Bs for memory since register 0 is always 0。

 there's 15 times 16 bits for the register and then there's the PC。

 So there's a grand total of 4328 Bs， so those bits can be either0 or one。

 so the total number of different states that the machine could be in is 2 to the 4328 power or that's more than 10 to the 1300th power。

 that is an enormous number and the machine could be in any one of those states and that state would determine some new state completely and uniquely determined。

That's such a huge number and we talk about this in the theory lecture as well。

 if you took every electron in the universe and put a supercomputer examining states for all its entire lifetime you only get to about 10 to the 19th states 10 to the 1300 is stupefyingly large number it means you need 10 to the 1200 universes every electron in all those universes running supercomputers and these are basic estimates you can argue with them and it doesn't affect the main point and the bottom line is we'll never know what a machine with 496 bits of memory can do there's so。

 so， so many more states than we'll ever see in the lifetime of the universe。So yes。

 4096 bits of main memory certainly enough to do something useful。Now。

 let's talk a little bit about some historical context。

So a very early computer was called the EnAC was being developed by Moley and Eckert。 It's often。



![](img/40e5352e13166c19bb6d42c1ceaf2ce6_1.png)

Given the distinction of being the first widely known general purpose electronic computer。

There's a lot of debate about this and you can read about other candidates as well。

 It had conditional jumps， it was programmable but it didn't have memory Programing was a matter of changing switches and cable connections so the back of the machine were cables and you replg the machine to get it to ready to perform a certain calculation and then the machine would crunch data and do things like plot of parabola to figure out where a missile would go or something of the sort。

The data came in on punch cards， so there'd be a lot of numbers on punch cards and the machine to read those numbers and compute with and that's how the AntiAC worked。

And that was a 30 ton machine that filled a room， it had vacuum tubes。

 it could do 300 multiplies in a second and a bit was a physical thing called a vacuum tube。

So there were a lot of obstacles to overcome in using a machine like this to solve scientific problems。

 but definitely it was running and working and helpful in preparing ballistics tables for use during the war。

Now， theres a famous memo that I want to talk about called First draft of a report on the EdVAC that was written by John Von Neuumman。

 a mathematician at Princeton。The EdVAC was the next computer that was proposed to be built by Eckerdon Moley and Vanon Neumman worked with them over the summer in 1945。

But he also was working at Los Alamos on mathematical calculations and simulations for the atom bomb。

 and he had to take a train to Los Alamos to write up a report on their work on the EdVAC。

It turned out that that memo was a brilliant summation of the concept of having a memory and storing a program in the memory and really a complete design of a computer that could do it。

 Now， Vanon Neumann had heard about the theories of Alan Turing and the idea of a program that could operate on another program as data definitely influenced his thinking on this。

 and it's influenced the design of every computer since。

 reading this memo particularly after you've done with the next few lectures where we talk about designing and building such a machine。

 it's quite striking how much is in this memo that we use regularly today。And every computer does。

And so the question of who invented the Stet program computer。

 there's really a fascinating controversy about that。

So Ecrdom Moley had discussed the idea before Von Neman arrived on the scene and discussed it with von Neuman in their joint work when talking about the design of the headV。

But Vanon Neumman wrote everything up and he was on a long train ride and he had every part of what he knew at his command。

 including the amazing theories of Alan Touring， he was in a unique position to put it all together and that's precisely what he did。

Now when Wa Neumman arrived in Los Alamos， a young Lieutenant Herman Goldstein circulated the draft because he could see what an amazing document it was and there was a lot of interest。

 but the public disclosure of that draft of the first the report on the EdVAC meant that that Ecu and Moley could not patent their design。

 in course they were not very happy about that。Von Neman never specifically took credit for the idea of storedward program computing。

 but he actually never gave credit to others either。

 so we're all going to have to make up our minds on this。Another example。

 just as an indication of the impact of von Neman's memo。

 just not very long after the memo was published， Maurice Wokeks in England built another machine called the Ed Sac and that one had lots of characteristics very similar to the machines we use today。

 the data instructions were load in binary， you could load programs。

 not just data into the memory and you could change the program without rewiring and those are all characteristics that we depend on and we'll come back to this later in this lecture。

That machine had 512， 17 bit words， not so different than Toy， two registers， 16 instructions。

 the input was paper tape， the output was not paper tape。

 it was a teleprintter and there a bit was a different kind of device。

 not a vacuum tube but still not that much smaller。

And this thing came into existence quite quickly because Von Neiman's memo so beautifully laid out the blueprint of what needed to be done。

So in fact， the architecture， the basic architecture of the stored program computer has been the basis of nearly all computers since the '50s。

So all the things that we use， your phone， server farm， PC， and toy。

 and the old computers all had this basically the same design that we're going to be looking at in the next couple of lectures。

The practical implications of a stored program computer is that we can download apps when you download an application into your phone。

 you're loading a program into the memory of your phone， seems so straightforward and natural today。

 but remember the first computer didn't have that capability。

The other thing is we can write programs that make programs as output。

 that's what compilers and interpreters are and many。

 many other types of programs that we'll talk about。

And you can also write programs that take programs as input and you can simulate other machines。

 that was Tring's a brilliant concept。So these implications are very profound as we discussed in a lot more detail in the theory lectures。

 with Toy， you can solve any problem that any other computer can solve。

 but you also have the limitation that some problems can't be solved by any computer at all。

All of this is by way of justifying studying Toy carefully。

 it's a simple machine that has the same characteristics of all the machines that we use。

 the only difference is a matter of scale， and that's what we're going to go into next is to look at some of these implications in more detail。



![](img/40e5352e13166c19bb6d42c1ceaf2ce6_3.png)