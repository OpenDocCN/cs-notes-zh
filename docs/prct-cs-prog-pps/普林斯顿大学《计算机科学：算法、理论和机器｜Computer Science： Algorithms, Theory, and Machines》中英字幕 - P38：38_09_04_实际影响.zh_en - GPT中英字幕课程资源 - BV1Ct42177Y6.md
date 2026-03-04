# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P38：38_09_04_实际影响.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/5f011f6dedc49bebd2a1e6dae6b72102_0.png)

Well， the idea that data can become code that has malicious effects is certainly a sobering idea。

 but there's many， many positive practical implications of Ho machines that overwhelm this。So again。

 von Neman architecture there's no difference between data and instructions。

 the same word can be data one moment and an instruction the next。

And immediately early programmers realized the advantages of this so and we'll talk in detail about a couple of these things so one of the first things was that once you've got a program keyed in with the switches you can save it on physical media it's just data and you can put it out on physical media and then you can load it at some other time just like we load the array。

 you can load your program that way so a program you might have to enter with switches only once and then you could save it and load it at another time and in fact that's how program development was done come in in the morning。

 load your program work with it by adding more routines patching it to jump out and then back in and so forth and then at the end of the day save the current state of the program with another dump and not too long after that in fact actually very early on people realize that you could develop higher。

level languages， and we'll look at just a simple example called assembly language。

 which made programming much more palatable on these simple machines。

The advantage of being able to treat code as data， data as code are really profound。

So here's the idea of dumping again we spend all day entering stuff with switches。

 but at the end of the day you have to turn the machine off。

 vacuum tubes can't be left on all the time， in fact the reliability of vacuum tubes was a huge problem in the early computers。

So what people did was write short programs to dump the contents of the memory to tapeate and again this code here is a simplified version of the code in the book which can do partial dumps and it's a little more general。

 but this is very much like the code that we just did for loading an array except in the middle at location4。

 there's 9 AFF， which is to write the current word to standard output。

 and this is a program that just sits in a loop， printing out the contents of memory。

 as long as from 10 to FE FF of course， is the standard input output location that we don't need to dump。

So that dumps the whole memory out to paper tape。Now this program we put in the first part of memory and then we just run it to save the data instructions in the rest of the memory The pseudocode uses 0 x10。

 that's a hex literal in Java code that maybe we haven't used。

 but we'll use a little bit later on and zero XFF is also used in the pseudocode。

So that's dumping a small program that we can implement that we put in the switches to save the whole contents of memory。

And then the next day， we reboot the computer。 We turn it on at the time you turn it on。

 everything's0。Because it just got turned on and then a programmer would key in this boot code。

 which is just like the dump code except that instead of writing from memory to the punch paper tape。

 it reads from the punch paper tape into memory， again。

 using indirection very much like the code that we looked at for reading in an array。

And then just run that and then it loads up the whole memory。

 you don't have to key in the whole thing and again you don't want to worry about the first few words of memory because you want to overwrite your own program that first few words of memory or always reserved for the boot code。

And in fact， a lot of computers of this kind would have this boot code scotch tape to the side because the first thing that people had to do every day was come in and turn on the computer。

 key in the boot code， load a paper tape， and then get their big program loaded。

 and then go ahead and do their work for the day， running the program on different data or debugging the program。

In fact， early programmers would do this every day or multiple times a day and people would pride themselves on how fast they could enter this code with switches with the switches on the front of the machine it's like playing a piano you'd be surprised how fast people could get at entering code particularly the same one every day in this way。

 so that's dumping and booting and it was definitely a critical part of the workflow early on but all made possible by the idea of a von Neuman machine。

 but then people realize well， actually we can conceive of a higher level language that we could program in and rather than putting in numbers we could actually work in what's called assembly language where we have mnemonic names for the instructions like LA for load address or A for add or S for。

Track BPP for branch positive and so forth， and then we could use symbolic names。

 even for the memory locations or the registers so that we can have the idea of branching to loop and labeling an instruction with loop。

So then we're not working with numbers， we're working with letters that when there were lots of op codes。

 that was helpful and we could work with symbols， not numbers for the addresses and one of the big advantages of this is that the code could be moved somewhere else in the machine without having to actually change the source code because would have a program called an asmbler that would figure out where the program starts in the memory and therefore what the value of a symbol like loop would be those were big advantages that made it worthwhile to write a machine language program to translate and you could write toy code that could take input like this with proper encoding for the symbols and so forth and produce the machine code。

 in fact on Wilk's machine， they early on had an。Assembly language in this way because it was so much more convenient to write in a higher level language and again this is a program that produces a program as output and again made possible by the concept of a vno machine people still write code in assembly language today because it directly maps to machine language code which is extremely efficient and it's important for performance critical applications。

And that's just the tip of the iceberg nowadays we use programs that process programs all the time again。

 if you have an installer and you're downloading an app。

 that's a program that loads a program into your machine。

compileilr translates your Java program into machine language simulators take code for one machine and make it pretend that it's another machine we'll look at that in a minute。

 you'd have compilers on a big machine that would produce code for a little machine and that was often very useful way to go dumping and booting while viruses we have that problem but the idea of virtual machines and highlevel languages is an extremely long list of practical implications of the idea that we can treat programs as data and it's certainly a critical part of our modern infrastructure。



![](img/5f011f6dedc49bebd2a1e6dae6b72102_2.png)

![](img/5f011f6dedc49bebd2a1e6dae6b72102_3.png)