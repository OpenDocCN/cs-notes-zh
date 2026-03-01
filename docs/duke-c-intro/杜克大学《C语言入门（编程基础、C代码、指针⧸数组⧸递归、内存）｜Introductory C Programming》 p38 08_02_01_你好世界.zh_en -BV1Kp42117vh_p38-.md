# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p38 08_02_01_你好世界.zh_en -BV1Kp42117vh_p38-

![](img/bd7c057ce39311d4d06a20b0ccb59370_0.png)

In this video， we're going to step through the process of writing code in EmX。

 compiling it and running it。 We're going to walk through assignment 4， which is to write。

 compile and run a program that prints hellello world。

 So here I am in the practice programming environment。 And if I do LS， which you may remember。

 shows me the contents of the directory， I'll see a read me。



![](img/bd7c057ce39311d4d06a20b0ccb59370_2.png)

I'm going to Emax the read me。And it's going to open up。And it says that basically what I just said。

 we're going to write a program the O print Hello World。And so to do this。

 I'm going to open a file called Hello。t C， so I hit control X control F， prompt me for the file。

 I' to type Hello do C。I need to put my header files at the top I need to pound include them。

 so I'm going to pound include standardIo。 H for print F。 I'm going to pound include standardlib。

 H for exit success and then I'm going to write main。

 which returns an int and for now takes no parameters later on we'll learn how to have it take command line arguments in Cose4。

And we want to print hellello world。 so I're going to write print F。Hello world。

 and I want it to have a new line at the end， so I'm going to put back slash in。Close my parentheses。

 Put a semicolon。I'm going to put return， exit success。I'm going close my curly braces。

 And then I'm going save this file with C X， control S。

 And then what I'm gonna to do is I'm gonna to suspend Eax。 So I can go back to my command prompt。

 So if I hit control Z and get back to my shell。 and I can type commands。

 We can also compile inside of Eax。 We'll show you that later when you learn about make files。

 And then you don't have to go in and out of Eax。 Sometimes you want to suspend Eax anyways。

 So I'm going to do Gcc dash O hello， just going tell it to make a program called hello。

 I'm want to give it all of the。Flas that we give it so that it will be very very picky about if I wrote good code。

And I want to compile Hello doty。Now， GCC didn't print anything。 That's good。

 That means it succeeded。 If I do L S， I will see this hello there。 It's green。

 which means it's executable。 so we can actually run it。 So if I type dot slash hello。

It will run and print out Hello world。 So now I would。Add hello dot C to get。 I'm gonna remove。

 Hello。 I don't really like adding binaries to get。 Usually I'm gonna commit。

And it's going to prompt me for a message， and I'm going to say that I wrote。Hello world。

Save that and quit。 And then I'm gonna push。 I'm going to grade。

 Now I'm gonna just note that we did all of this with Emax suspended。 We didn't actually quit Eax。

 It's still there。 So if I type FG， we'll be back in emax where we were。

 If you're doing this and you suspend ems， don't start a whole bunch of copies of ems for other things。

 So if I wanted to keep editing my code， I could do that here。

 But I've finished this assignment and I've passed it。

 and now we would move on to the next assignment， which is going to involve writing some code that prints out squares。



![](img/bd7c057ce39311d4d06a20b0ccb59370_4.png)