# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p66 14_03_01_缓冲区溢出.zh_en -BV1Kp42117vh_p66-

![](img/67f5d46255f4a680e31f8b7e296ea62d_0.png)

Now， we are going to take a moment to look at the mechanics of a serious and common security vulnerability。

 In this code， a sloppy programmer used the GiS function。

 You should never use giS as it has no way to specify the maximum number of bytes it should read into a fixed size buffer。

We'll step through this code with a look under the hood instead of our usual， more conceptual model。

 In general， when we violate the rules of C， we have to look under the hood to see what might happen and why。

We're going to start with a quick tour of the stack layout as we've drawn in here。

The layout of the stack frames under the hood is very platform specific。

 but this attack can be adapted to most platforms。 This line separates the frame for main at the bottom。

 from the frame for its collar at the top。 Main gets called by part of the C library。

 There are probably values other than 0 in that frame。 But what they are， doesn't really matter。

Here we have ArgV， which is an 8 byte pointer， it pointed an array of strings。

 which is not pictured here。Then we have Arg C， which is a 4 byte integer whose value is 1。

Then we have the return address， which is an8 byte pointer。

 that points somewhere in the code for the C library right after it called Maine。

The code in that part of the C library will call exit passing in the return value of main。

Now we'll start execution at the start of May， we declare input。

 which will be these next 12 bytes in the stack。Then we call Gdes。

 which is somewhere in the C library。The programmer expected that the user would input something less than 12 bytes。

 such as hellello， which would write these bytes into the first part of input。

But what if the input is longer than 12 characters。

 Gdes has no idea how much space is actually allocated to input。

 So it will just keep writing data into the next addresses on the stack。

 Notice that the return address is on the stack。 What happens if you overwrite that。

 You'll change remain main returns。 That seems bad。In fact。

 it is particularly bad if the input is carefully crafted by an evil hacker。

 in which case it might look like this， where I've written nonprintable characters as back slash x and a hex value。

 Don't worry about the specifics of this data。 I made it by writing and compiling the code I wanted to trick this program into executing and saving those bytes from the executable。

So what happens？The first 12 B are no problem。 They get written into input， as we'd hoped。

 but this input is longer than 12 by。 The next 8 B of the input overwrite the return address。

 Notice that the value we overwrote it with looks like a valid pointer into the stack。 In fact。

 that pointer is the address of Arg C。 which is important since we continue to overwrite Arg C。

And overwrite A V and then overwrite the data in the colors frame。

Notice we finally read a new line which has numeric value Hex0 a。

 and then get us wrote a null Terminator， which has value Hex00。Now gides is finished。

 so it returns to main， which prints from input until it finds a null terminator。

So it will print some letters and then some non printable characters。

Now we are ready to return from Maine， usually our program would exit。

 but that is because it would return to the C library code， which exits the program。However。

 since we corrupted the return address， we're going to return to the address it specifies and keep executing code there。

That address is right here on the stack and contains the carefully crafted data that the evil hacker entered。

 So when we return there， we will start executing whatever instructions correspond to the values that the hacker entered。

 This particular set of instructions was crafted to execute the command shell。

Imagine if the code were part of a network service and an attacker were able to get a shell on the system from their buffer overflow。

 They could then execute any commands they want。 The moral of the story is to never use giss and be careful to never allow buffer overflows。

😊。