# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P45：45_11_02_概述_3.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/7a71ceda3a5651f933380e7b683fb189_0.png)

Today， we're going to put all these concepts together and try to give you an idea of how the central processing unit in your computer works。

'Start with a brief overview to put things into context。

So what we're going to do is build a computer。 Well， actually。

 we're going to talk about the central processing unit of the computer。

We're not going to worry that much about the keyboard or the display or the trackpa or anything like that what we're going to focus on is what makes the difference between a TV set in your computer and that is if you pry your computer open and look inside there's a thing called the motherboard and in there's a big square device which is an integrated circuit chip and actually implements a circuit known as the CPUU and what we want to look at is a circuit that implements the CPU。

Now in the last lecture we talked about combinational circuits。

 which and we ended up with an implementation of the ALU， the calculator part of the computer。

 in this lecture we're going to talk about memory and to implement memory we need so-called sequential circuits which have feedback that'll enable us to implement the other components of the CPU circuit and put it all together。

Now we're going to do this for a smaller computing machine even than toy that we call toy8。

 so remember the basic toy instruction set architecture， which we spent a couple of lectures on。

 there's two types of instructions， op code and three registers or op code register and address。

 the machine had 256， 16 bit words of memory， 16 registers， a program counter。

 and 16 different instructions。For today， we're going to look at a smaller version of toy called toy 8。

In this computer you might think of as an earlier version of toy。

And it has just 168 bit words of memory and just one8 bit register there's 16 different words of memory。

 so that means we can access any one of them with four bits that's the program counter and there's just going to be one type of instruction that's with an op code and an address in just eight different instructions。

 so eight different instructions we need just three bits to specify one of the instructions。

16 words of memory， We just need four bits to specify one of the 16 memory words。

 and we actually have an unused bit in the Toy8 instruction set。

 and you might imagine that as at the time that we're building this computer。

 we're not sure whether it's going to be more important to us to have more memory in which case we'd use the bit as part of an address or more different instructions in which case we'd use the bit as part of an op code and this actually indicates a reality at the time that people were designing early computers。

But our main reason for doing toy 8 is that the circuit that we wind up with is small enough to fit on a single slide wouldn't quite be the case with toy。

We'll come back to that， but we're going to illustrate the full CPU circuit design of this computer。

 which is only differs from many kinds of real computers just in a parameter which is essentially the size of the memory。

With the design， a full understanding of the design at Toy 8。

 you could understand the design of the full toy or even your own computer。

So toy 8 is a different machine， so we'll start by describing completely what toy 8 is。

 and as we did with Toy， we'll do it with a reference card that completely describes every instruction in toy 8。

Now we're going to use Hex as we did with Troy， but now there's only8 bits in a word。

 so that's two hex digits。One for the address， on the right and the other for the op code on the left。

Since we're assuming that the last bit of the op code， the fourth bit of the word is zero。

 then our op codes are all even so for example the addd instruction， the op code is 001。

 but the hex digit that we use to represent it is 0010 or 2 so all our hex digits are even。

Then the pseudocode， as before， as with Toy gives the action of each instruction。

 the main difference from toy is that where in Toy we had multiple registers and the instructions operated on those registers and referred to them in toy8。

 the arithmetic instructions take the results of performing the operation on the contents of the register and a specified memory word and put that result back in the register。

So the add instruction， Op code2 replaces the contents of the register by the sum of what's in the register and in the memory word。

 and the bitY Z， the Op code 4 and bitY X or Op code6 work in the same way。Then we have load address。

 that's Op code 8 where we take the four bits at the right of the instruction and just load those into the register。

 and then we have load where we use the address to reference a word of memory and we put that word of memory in the register and then we have store where we do the opposite。

 we use the address to refer the word of memory but we store the contents of the register in that word。

 and then we have a branch instruction which tests if the register is zero and if it has changed the PC。

main thing that's missing from toy here is the shift。

 shift right disease to implement with a shift left is more challenging and so those are exercises。

 but you can implement quite a few of the same programs that we implemented in toy with toy 8， again。

 the main restriction is they only have 16 words of memory。

So but still all the basic functionalities there， the at arithmetic instructions。

 the references to memory and the conditional branch。Well， in Toy 8。

 we assume that memory location zero is always zero。

 we'll have standard input so we can load from memory location F and standard output stored to memory location F。

And with this information again， with experience in toy and other programming languages。

 we can all write simple toy8 programs， so here's an example of a toy8 program this is your first program in toy where we have two numbers that are in memory in this case location memory locations five and six and what this program does is add those two numbers and then put the sum back into memory。

So the first instruction is load instruction that's you can tell from the first digit。

 first digits of instructions are always even so that's a load instruction for memory location 5 then in location2 is an addd instruction where we take that number what was in memory 5 and we add it and put the results in the register add it to the number in location6。

 but the results in the register then the third instruction is a store instruction where we take the register and store it in memory7 that's Opcode C。

 and then fourth is a halt00， it's actually fewer instructions than in Toy where we had to load both registers before we could do the ad。

So and again， after executing that load， Reg 5 has the number five， and after executing the ad。

 it's got 8 plus5， which is D， and after executing the store that result goes into memory location 7 and then we're at a halt。

So a very simple program program is a list of 15 or fewer two digit hex numbers。

 doesn't seem like much， but on the other hand， if you enumerate all the possibilities。

 there's way more Toy eight programs than we'll ever see and you can go ahead and write programs that write the Fibonacci sequence of standard output。

 add numbers and so forth。The 16 word limit is definitely a limitation。

 but still there's a lot that you can do。But we're not advocating that you write programs just that you believe that this program is sufficiently similar to toy or to a real computer that understanding how to design a circuit that implements toy gives great indication of how to design circuit for a computer that's got more memory and registers and instructions。

Okay， so the circuit components that we have to implement are really based on circuit the components that we describe when we describe the machine。

 there's an ALU that implements add and an XOR， there's a memory there's the register。

 there's the PC and instruction register， and then in this lecture we're going to introduce two new components。

 one called control and one called clock， the clock is what drives the machine to do one thing after another and control is what translates those sequences into instructions to all the components to change their state to implement the instructions and that's what we're going to focus on in this lecture。

We want a complete CPU circuit for Toy8 that implements all these components， connects them together。

 and gets the instructions executed。So just to review， this is a slide from the last lecture。

 all of our components are major functional units。 we're going to have certain conventions so we can easily identify what they're doing。

They're blue boxes， they take their bus input， so that's the contents of a word usually or an address and those come in at the top and we always connect to the components at the left。

Then the outputs are at the bottom and we connect from the components at the right。

 and then we have control lines that are in blue that cause the components to do things。

so we implemented our ALU in this way in the last lecture。

 and in this lecture we're going to implement the other components and then talk about how to connect them together。

And again， we could make the circuits a little bit smaller by rotating these things and packing them together and not having this come in at the left go out at the right top and bottom convention。

 but those packed up circuits are a little bit harder to understand It's like style conventions and coding you can use way fewer characters in your program。

 but it becomes a a lot more difficult to understand would do the same way with the circuit and our circuits are only maybe 50% bigger than they would be otherwise so it's not a big thing。

Okay， so we're going to adhere to these conventions so now why do we bother go to toy 8 when we already had toy Well the main reason is that the toy circuit would be would be huge or if we try to put it on a slide the components would be small So it'd be about maybe five times as big as the toy 8 is an estimate so it's kind of not worth it let's go to toy 8s where you'd be able to see every switch and then you can imagine that toy is going to be very similar and most of the space is taken up by things that are extremely similar like memory bits。

Toy 8 has with its 168 bit words， just has 16 times 8 is 128 bits of memory。

 whereas toy with its 256， 16 bit words has 4000s of memory that's where and those are all the same so there's kind of no point and including all of those things in the diagram of the whole thing。

Now it's a kind of a sobering fact that your computer is maybe I don't know。

 several hundred or1 thousand times wider than toy8。

 so these circuits are extremely tiny compared to what's in your computer， but again。

 most of that is very regular thing like memory bits that don't add much insight to how it's really working。

 so that difference is not really that significant when we're talking about the design。

 which is all three of these are based on the same fundamental ideas and that's our purpose is to try to explain these ideas。



![](img/7a71ceda3a5651f933380e7b683fb189_2.png)

So next we'll get going and take a look at the basic idea of how to implement a memory。



![](img/7a71ceda3a5651f933380e7b683fb189_4.png)