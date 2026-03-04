# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P13：13_04_02_标准输入与输出.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/f0a06b21f09d6352523720c208bc2889_0.png)

Today we're going to talk about input and output， Most of the Java programs that we've written so far are mostly inwardly focused。

 where we generate random numbers with the program and then maybe write code to compute statistics from it。

In the real world， what we want to do is process data that comes somewhere from the real world。

 take it as input and then produce output that meaningfully expresses the result of the computation。

 so we're going to talk about Java mechanisms that allow us to do this along with some libraries that we've written。

First， we're going to talk about something called standard input and output。

 really the basic mechanism for communicating with your program。

This adds again quite a bit to our basic building blocks for programming。

 we've already talked about standard input and output for text。

 but now in this lecture we're going to open up a whole new world by talking about writing programs that can manipulate sound and images and graphics and we'll have plenty of examples of that later on。

So the goal is to write Java programs that interact with the outside world in some meaningful way using input and output devices that are connected to the computer。

There's all different types of input devices we've been using the keyboard in there。

 maybe there's storage or a trackpad， maybe the internet itself， camera， microphone。

 all different types of devices exist and are connected to your computer for providing input and we want to get that input to your program。

And then we want to provide output so we can do it on the display or maybe in a storage device or out to the network or to a printer or maybe speakers。

 so our approach to get this to happen for all these various devices is to define abstractions for input and output and we'll talk about what that means。

 and then use the operating system functionality based on those abstractions to connect our Java programs to the actual devices that you might own。

Abstraction plays a really essential role in understanding computation。

 and we'll come back to it again in this course， but this is a fine example。

An abstraction is something that exists only as an idea。

So if you want to think more deeply about that， take a philosophy course。

 we'll go at a level that's quite intuitive when we talk about this。

 so in this example the idea of printing is that's really it's the idea so far the way we've discussed it of a program producing text as output。

So if a good abstraction like this one simplifies our view of the world because it unifies lots of diverse real- worldor artifacts。

 We're not specifying precisely how the text gets printed on precisely which kind of device from the point of view of your program we're just talking about printing in that same program can produce results on all different types of devices。

 the abstraction that the program works with is printing。

 It's up to the operating system to realize that abstraction in the real world depending on the actual device。

 So we're going to talk about a number of different abstractions besides just printing for delivering input to or receiving output from our programs。

So it's quick review we've already done this to get started。

 so we had the idea of a terminal which is an abstraction for providing typed input and output to a program and we talked about the terminal window。

 that's an idea that's not actually a terminal in the ancient times we actually had a terminal called the VT100 and you interact with that terminal window and pretty much the same way that people used to it。

 interact with VT100s decades ago， but it's an abstraction。

 it's an idea let's type stuff to our program and let's get typed output and we use that to run a program。

 provide some input on the command line and get some output in the standard output stream。

So input from command line output to the standard output stream。

 so that's what we've done so far just a high level view we have this mental model of what a Java program does。

 it takes some inputs from the command line arguments and it produces output on the standard output stream。

 We're going to significantly enhance this diagram during this lecture。

So command line input is an abstraction for providing strings really to a program。

The properties are the strings that you type after the program name are available at runtime as AG zero。

 as 1， and so forth。Those arguments are available when the program begins execution。

 that's how command line input works。And we call the system conversion methods to convert those strings into integers or doubles or other types of data。

So we had a program called Random int that takes its value n from the command line。

 and so that's an example of the use of the command line input abstraction。

We type an integer and it gives us a random integer in that range。

 that's our review of command line input。Now， in standard outputs。

 the other abstraction we've been using。 So before we talk about standard output。

 there's the idea of infinity。 Now that's an abstraction too。

 that's describe something that has no limit。And that's important because the standard output stream is an abstraction for an input。

 an infinite output sequence。 That is an output sequence whose length has no limit。

 We just keep writing to standard output From the point of view of our program。

 There's no limit on how much it can write out。And so we take strings from standard system out that print line。

 we add them to the end of the standard output stream。

 and the operating system connects that to the terminal application by default。So if we wanted。

 we have this program for printing a random sequence of integers。

 so this time we take an integer in and we print that many random numbers on standard output。

Program takes a number to print from standard input。

 but otherwise it has no real limit on the number of things that it might print。

 and if you wanted to print a million numbers on standard output， you could go ahead and do that。

Those numbers might get printed in some other way， but that's from the point of view of the program。

 it just uses the abstraction known as the standard output stream。

So now we're going to look at an improvement to that where we add an infinite input stream。

So here's what we do now we're going to provide something like standard output has no limit。

 but it's input to the program， not just output。So how does standard input work， again。

 it's infinity， it's no limit， so it's going to be an abstraction for an infinite input sequence。

Command line is kind of like that， but all appearing on online and there might be limits and it appears at the beginning。

 so the big advantage of standard input over the command line is the new data can come while the program is executing and we'll take a look at that same way as we print stuff out while the program is executing and again no limit on the amount of data we can provide to a program。

The other thing， the way that we've written the libraries is that the conversion to primitive types is explicitly handled and we'll show you how that works。

We built a library for this course to implement standard input。

 This abstraction has been around since the 1970s and we felt that for effective Java programming。

 it's important to have quick availability to standard input it's built on basic Java mechanisms。

 but we wanted to make the ability to read infinite numbers of ints or doubles or strings easy for every Java programmer。

 so the software that you download it from our book site at the beginning of the course has this library。

It's called standard N。And it supports these methods， so there is empty if is the input stream empty。

 and then there's read int， read a value of type int， read double， read a value of type double。

 read long， read Boolean， care。String。And read all is read everything。

See there's a couple of other methods that you can find by looking at the documentation in the book or on the book site。

So now let's look at some programs that use these methods。

 which are very natural in this documentation。To match standard input we also develop standard output it's pretty much the same as system dot out and from now on we're going to use standard out instead of system dot out so why do we do that Well we're going to put all ourIO abstractions right in one place for use and so that you can go right there to figure out what you need to do for input and output and we have more control over standard out because it's ours and we can provide consistent independent of the system output where system dot out has some dependencies in language and locale and other things。

So standard in and standard out are our abstractions for infinite input stream。

Infinite output stream。We're going to stand it up from now on let's take a look at just。Wma。

So the first thing is to show that we can do interactive input with standard input。

 so what you can do is write code that prompts a user to type some input and you can also mix the input with the output stream so this is just a very simple example if you want to add two numbers so you can print。

 type the first integer that's a prompt to the user。And then read the integer that the user types。

Standard in that read in。 And that results in an integer value that we assign to the variable x。

And then print， type the second integer and get the second integer。

 then you can compute the sum in the program and then print that their sum is and then print the answer。

So that's a simple program where we mix input and output on standard in and standard out。

So if we run this program， the program runs before we provide any data， then we say， well。

 let's add one and two and it'll say there sum is three。Very simple application。

 Let's look at a more interesting one。 Let's average the numbers on the standard input stream。

So what we're going to do， we want to read a stream of numbers and compute their average。

So here's the code for doing that， we're going to have a double variable sum that keeps track of the cumulative total of all the numbers and we'll count them the inte of variable n there'll be the number of values。

 so while standard input is not empty。We're going to want to read a double value。

 put that in the variable x。Update sum by adding X to sum and update N the number of numbers we've seen by incrementing。

And we stay in that while loop reading numbers until standard in is empty。There could be 10 numbers。

 There could be a million。 There could be a billion from the point of view of the program。

 there's no limit。 It'll keep reading numbers from standard input until standard input is empty。

And then after it finds that the input streams empty， it's read all the numbers。

 then it just prints out the average sum divided by n。

So Java average we can type in some numbers and the first question that comes in is。

 well I can type in numbers but how do I tell standard input that I'm at the end of the input stream how does it know Well for decades the standard has been you type control D nowadays this is a little bit systems dependent so you might have to look that up and try a few things for your system for example on Windows it's control Z。

 but once we get by that easy to specify the end of the input stream and then it'll just print out the average？

So from this program has no dependency on the number of things in the standard input stream from the point of view of the program that's infinitely long。

 that's a very key point， it means that we can write a program in today and still have it used many years later。

 when there's much more possibility of much more input many people have written programs decades ago that were intended to handle just hundreds or even thousands of data points。

 those same programs can now handle million or billion data points with absolutely no change because of the standard input abstraction。

And again， input and output can be interleaved， we have to remember that。So here's the summary。

 we've seen two prototypical applications of standard input and standard output for standard out。

 it was generate a stream of random numbers and for standard in。

 it was compute the average of a stream of numbers。

 This one puts out as many numbers as it wants this one takes in as many numbers as are there。

 and the key point to remember is that both streams are infinite。 there's no infinite。

 There's no limit on their size。So a natural question comes up is。

 do I always have to type in my input data and print my output in the terminal window？

And the answer to that of course， is no， what you want to do and what people always do is keep the data and results and files on your computer or maybe some external device so we can talk about that。

 and then there's the concept maybe you don't even have to do that。

 there's the idea of piping to connect programs。Again， these ideas go back to UniX in the 1970s。

 but they're still broadly useful， we're providing the mechanisms for you to use them within your Java programs。

So let's look at how we can put results in files and how we can connect programs together。

So keeping files on your computer takes advantage of a mechanism called redirection。

 which is supported by your operating system。On the command line， if you put a greater than sign。

 what it means is。Redirect standard output to the file that's named after the great event sign。

So if we say Javaranom seek a million redirected to data。 textt。

 we don't get anything printed in the terminal window because we redirected the output to go to that file。

Then later， if we look at what's in that file， there's the million numbers。

Very simple way to get data produced by your program into a file， redirect standard output。

So this is just a schematic of that， our program randomand seek produces output。

 the standard output stream gets redirected to a file instead of to the terminal window。

And the mirror image of that is you can redirect from a file into standard input。

So if we use a less than sign after the program name on the command line。

 that says take standard input from the file that I'm going to name。

So if we run Java average and take standard input from that file with a million numbers。

 we get a result that's close to a half that we hope。

So that's connecting the programs through the file。

The file goes on a standard input stream into average。

So that's an extremely convenient way to compute and we're going to see lots of examples where you want to do that。

There's still a slight problem is that we don't really have that concept of infinity because the maximum file size is going to restrict us in any real kind of situation。

So we want to have this other idea called piping， where we don't save the data at all。

It's just the abstraction of standard input and standard output lets us compute with an unlimited amount of data。

 maybe we're only limited by time。So there's no room for a huge final computer。

 so what we do is use piping and what that does is just connect the standard output of one program to the standard input of another。

So in our example， we can， if you， after you issue a command， you put a vertical bar。

 that means set up a pipe and it does exactly what this says。

 connect the standard output of that program to the standard input of the other one。

So now we're generating a million numbers， but we're not saving them anywhere。

 We're not printing them on the terminal。 All we're doing is providing each number to the other program when it asks for it。

 So now we can run this experiment for a million numbers a lot of times or a billion numbers without ever saving the numbers。

 We connect together the standard input stream and the standard output stream。 Again。

 this is a very convenient way to compute。 Neither program is concerned with the amount of data that is going to process。

 but we have the ability to have the program' process an unlimited amount of data。

 No limit within the programs of the amount of data that they can handle。

There are an awful lot of old programs that were written this way that are still useful because of the standard input and standard output abstractions。

It's the job of the system to figure out how to collect the data temporarily on standard output and provide it to the other program on standard input and it's going there might be some restrictions or some difficulties in doing so but the whole point or the whole job of the system is to provide this abstraction for the programs there's lots of other abstractions that systems provide for programs this one is a particularly convenient one having to do with input and output of text。

And it's interesting to contemplate because nowadays we're awa in data and we need to consider algorithms of this type all the time。

 but it mirrors what people faced in early computing。

 early computing there was very little memory available each bit had to be physically touched by somebody and after a while there could be more memory。

 but the amount of memory available was way smaller than the amount of data that had to be processed。

That's what led to the development of these abstract mechanisms because there were dramatic increases happening every year and with the redirection in piping。

 it meant that your program could handle way more data than could be stored in the computer。

And we'll look a little more at that later on， so you could have standard input and standard output connected to devices that are external to the computer。

 for example。And that's an example of one paper tape punch and we'll look at that later on in the course。

 so standard output would be connected to a paper tape punch to put the data on this physical medium outside the computer again the amount of data is only limited by the amount of tape that you have and then standard input would connect if paper tape reader to standard input and then the program could read unlimited amount of data again only limited by amount of tape there is and that was extremely effective in building up more complicated programs a more complicated data processing applications。



![](img/f0a06b21f09d6352523720c208bc2889_2.png)

But in modern computing， it's the same thing， we have the web， we have oceans of information。

 there's no way that you're going to fit the data that you want to process in many。

 many applications in any available computer memory。

And we're still getting dramatic increases every year in the amount of data that's out there that we want to process。

 so what they're called now is streaming algorithms where our program can handle a lot more data than our computers can store。

 but they're based on getting started with abstractions like standard input and standard output。

So the lesson is whenever we can， we're going to try to avoid limits within our program whenever possible。



![](img/f0a06b21f09d6352523720c208bc2889_4.png)