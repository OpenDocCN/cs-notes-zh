# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P37：37_09_03_注意事项.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/629bb08cdd550a5f798e6f94357691c6_0.png)

Next， we're going to look at a sample program implementing a arrays with toy。

 and at the same time sound a note of caution about Faonuumman machine。Okay。

 so to implement an array， we're going to use the same basic idea that we talked about in a more abstract fashion when we introduce as for Java。

We keep the items contiguous in memory， starting at a given memory address。

 So this is an array of 11 elements that are stored in memory， starting at location 80。

And the way that we'll get to the I element of the array is just add I to the address of the first element of the array so a of 2 is at 82 80 plus 2 and so forth。

 so it's a simple calculation to get to the point where we want to know about the contents of an indexed array element we're going to use indirect which is built into the toy instruction set to facilitate this。

So the idea is we're going to keep the array address in a register and then when we want to access an array value。

 we're going to add the index and then use the indirect load and store instructions。

 which use the contents of a register rather than an address within the instruction to reference a memory。

So these are the three instructions 7， A and B from the Tore instruction set that we're going to use to implement arrays。

 load address， loads the address bits of the instruction into the specified register。

Load indirect load uses the contents of the specified register as an address and loads the memory word at that address in store Indirect does the same for store。

So for example， here's an example of an indirect store。So 7 A80 loads the address 80 into register A。

 that's where our array starts。And then we'll have another register， say register nine。

 that is the index into the array， usually we start that at zero and are minute until we get to the end of the array。

So later on， in the code somewhere after Reg 9 has been incremented to some other values， say。

 we're going to have this kind of calculation。1 CAA9 that's an ad instruction。

 a destination register is C and registers A and 9 of the two to be added。

 A's got the address of the beginning of the array and9 has the index。

 and so we add those then we'll get in Reg C， the actual memory address that we want to reference。

And then the store indirect instruction B is going to take Reg D。

 the contents of Reg D and store that in memory， but the place that it's going to be stored in memory is not in OC。

 since it's a store indirect instruction， it'll be the address it's in Reg C。

 and that's the one that we just computed somewhere in the array， maybe 84 or 85 or something。

And then maybe we increment eye and then continue on our way。

 so we'll look at this code and context on the next slide。

 but that's the basic idea using the load indirect and store indirect instructions in computing the address of the memory word that contains the index array element。

So here's code that reads an array from standard input。So again。

 we're going to keep the items starting at memory location 80 that's burned into this code。

 we start with Reg 9 equals0， and then we're going to access the I element in the array by computing by adding a plus I and that's how we access A of I。

Just a note， this example is simpler than the one in the book for the lecture。

 the one in the array processing in the book has includes the length of arrays in the representation more like Java so that we can pass arrays as arguments and return values from functions as we do in Java and you can see that in the book for now we're going to work with this much simpler code where we have location of the array built into the code and we don't carry the length along。

 but that's this code is easier to understand and quicker to describe and then you can read more general code in the book。

So here's our Java pseudo code for that so we do read in the length from standard input。

 so our array representation on standard input is a length on integer followed by that many array words that are be stored。

So the address of A0 is going to go and register A and the index is going to go in register  nine。

So our while loop is going to compare register9 our index against register B。

 which is our value of n， the length of the array， so as long as so by subtracting them。

 if we get to zero， then we branch out of the loop with this branch of zero instruction。

Otherwise we go ahead and compute our array index， read another word from standard input and then use an indirect store to store that in the array。

 then we increment I and then stay in that loop， incrementing register9 reading a word from the tape and storing it。

 using indirect store in the array until we've loaded up all the words and we get with Reg 9 register B equal we'll do a simulation of this code on the next slide。

So here's the same code and now we're just going to dynamically simulate it so we start out register one gets one which we need to increment register B will read。

Off the tape， we'll read the length of the array， which is6。You can see over on the right。

 the tape moved up to read the six out of the array。Register A gets 80。

 that's the beginning of the array and register9 gets zero。

And now we're going to go through the loop where we compute an array address in Reg C。

 we read a word from the tape into Reg D， and we store that word into the memory Add as reference by Register C。

So again， register 90 and register B is6， so the result is not zero， so we go into the loop。

 C equals register A plus Reg 9， which is just 80 in this case。

 and now we'll read the first word of data off the tape。And that's a one。

 and so we read that off the tape， and put it in Reg D。

And then we use the indirect store to store that word from Reg D into location 80。

 and that gets stored in Reg 80。Then we increment register nine to be one and now go back to test if we're done with the wild loop yet。

And now we'll just look at what happens all the way through the loop each time。

 each time we compute a new address in Register C， read another word from the tape into D。

 store that in memory and increment register nine。And in this way with this code。

 we read all the words from the tape until we get to register 9 equals 6。

 and it's equal to register B， we subtract them， and then in the instruction of location 15。

 we branch out of the loop。So that's a typical example of getting data from a paper tape into memory and again in the book you'll see a more complicated example where you can use this to create a memory representation of an array that you can pass to a function that you can process the array by computing sum of the elements or whatever else you might want to do。

Let's imagine a typical scenario which actually held true for many scientists when the first computers came along。

 let's say Alice develops a procedure for her experiment and she has a scientific instrument that's connected to a paper tape punch like Doug's father。

So what she's going to do is take the paper tape to a computer to process her data。

 Now the big advantage of the computer over the old calculating machines was that you could write a program and use that program to process the data。

 so she'd use code just like what we just described to go ahead and load her data and then have code that processes the array to analyze her data and produce some kind of output very typical scenario。

Generally， in this kind of situation， you'd have a lot of data and once you got the program going well。

 you wouldn't change the program much。And then maybe punch out the results on paper tape to save them。

 and that would be a natural workflow for a scientist。Well。

 let's suppose that Eve has some experiments and realizes that the same kind of analysis that Alice does would be useful for her too。

 so Eve says hey， Alice， could you process my data in Alice being a trusting soul says of course。

 sure， so then Eve gives her a tape and actually maybe the computer was slow。

 maybe not even Alice gets the tape， some computer operator loads it up and walks away or maybe Alice is standing there watching？

So let's take a look at Eve's tape now of course maybe you wouldn't do that you just take the tape。

 but if you look at this tape it looks a little fishy so the first thing is that it says it's got 256 words。

 there's only 256 words on the whole computer so that should be a clue that something might be wrong。

And then there's 146 words on the tape and they're all8s， so that's a little peculiar。

 what kind of data is that？Again， if you didn't actually scrutinize the tape， maybe wouldn't notice。

 and then there's something suspicious at the end。But that's a tape that could be presented to Alice's program that reads in the data and processes era with no problem at all。

 it's input to her program， so let's look at what happens。Is not at all what Alice might expect。

First thing that happens is well you're supposed to read the stuff from the tape starting at memory location 80。

 so sure enough it just reads and it fills up memory with all eights。

All the way up to the end of the memory。But actually， when you get to FF。

That punches something out on the output， that's a little suspicious。

 right because that's a punch on standard output。And then the address overflows back to0。

 and then memory locations 0 through0 f are overwritten with8s。

But that's when things really start to get bad。So let's take a look now at what happens。 So again。

 it's the same code for loading things from the array。

 So now we're at a position where we just read the an 888 from the tape and stored it in memory location0F。

And now the next time we're going to get another 888 and store it in 10 well that was our code where we set register  one to one。

And next time we put another 888 there， now this is looking ominous and it should。

 and then now it's not just8s， it's something else。Now there's a 98 FF。Actually， maybe it's not data。

 maybe it's code。 Well， actually it's both it's data because it was read off the tape。

 And now in the position where it is， let's take a look at what happens now when we increment the PC。

We increment register 9 and now we branch back to location 14 Lo 14 used to be the instruction that subtracted Reg 6 from Reg9 to check in Reg 2 if it's zero。

 but look what's there now， it's a branch instruction back up to location 12。

So what has happened is that Eve has taken over Alice's computer with a loop that just writes 888 on the output。

 an infinite loop。So if Alice had gone away to lunch。

 you would come back to find all our paper tape laid out on the floor with 8888 punched on it。

 This seems like a fantastic example， but it's actually quite a real example by taking a look at this carefully in understanding the idea that we took code from our。

Input data， it looked like data， but it turned out to be code。

 that's a key concept in a von Neumman machine。 you should be able to do this。

 otherwise we couldn't write compilers and interpreters and so forth。

 but there's a danger and this is the danger。Eve could have loaded any program at all。

 completely taken over Alice's computer， and in fact， this still happens to us today。

This idea that a hacker can own your computer just by presenting data to one of your programs。

Is a property of vanuum machines that lives with us today。

Here's a simple and actually widespread example in language C， C++ objective C。

Has exactly this problem called the string buffer overflow problem so here's some C code and again we haven't talked in detail about C code but you can get an idea the char buffer 100 statement declares a buffer that's big enough to hold 100 characters and then following that is a scanF statement that reads a string of characters for that buffer from standard input but this code doesn't check that the string will fit if there's a longer string then it'll overflow that buffer the system doesn't check either so what happens is the memory representation has the buffer stored at the beginning of the code and then control when the control for the first instruction is after that and that's where the code for scanF and printf and the rest of the code of the routiner。

 so what happens。Is that when the hacker reads in a long string， the hacker can put code there。

 which is the hacker's own program， just like EveV did。And at that point。

 when the system transfers control to that place， which was overwritten by the hacker's long string。

 the hacker owns your computer and can do anything at all with it。

 has control of the instructions that are run on the computer。

This was a first famous example of this was in 1988。

 a virus like this called the Morris wormm infected research computers all through the United States。

On 2004， there was a thing called the JPEG of Death that if you were in a Windows browser and you hit a certain image。

 it would overflow and the code at the end would transfer to hacker's code and that hacker would own your computer。

And people figured out how to get unlicensed games the same way with a buffer over overflow attack like this where people could see that the code doesn't check for a buffer being too big and then they could write their own code to get loaded into the buffer in just the program thinks it's reading data and the hacker owns your machine this is still true and iOS devices that it's listed as the top five vulnerability。

 there's lots of code out there and unless the programmer checks for this。

 then that code is v to this kind of hack。Now with Java， we try to write secure code。

 we try to check the bounds of arrays so that the compiler will tell us if we do this by mistake and also the types of things is another check against。

Miicious code like this， but as we discussed in the theory lecture。

 there's no way to avoid this in general， it's a fundamental consequence of the idea that data can later be executed as code。



![](img/629bb08cdd550a5f798e6f94357691c6_2.png)

![](img/629bb08cdd550a5f798e6f94357691c6_3.png)