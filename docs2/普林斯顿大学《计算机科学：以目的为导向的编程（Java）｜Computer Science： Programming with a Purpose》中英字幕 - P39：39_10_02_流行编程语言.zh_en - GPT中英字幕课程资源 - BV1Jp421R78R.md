# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P39：39_10_02_流行编程语言.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/3c9f190028ffded25cebf345c68aec83_0.png)

Now that you've learned a program in Java， we're going to finish this part of the course by putting what you've learned in context with other programming languages that you might have heard about。

First， we'll take a look at some popular languages。We begin with a story about the Tower of Babble。

 This is a story about the origins of multiple languages that you may have heard about。

After the flood， the whole earth was of one language and one speech。

And they built a city in a tower at Babel， believing that with a single language。

 people will be able to do anything that they imagine。

But Yaweh disagrees and confounds the language of all the earth。

 And so the question to think about is why。Why would he do that？And the answer is that。

The idea is that proliferation of cultural differences and multiple languages is one basis of civilization。

 We'll come back to this story， in just a minute。Now just as a starting example。

 if you want to get from one place to another， there are a lot of different ways to do it。

 you could use roller skates or a bicycle or maybe a car or maybe you need an allw drive vehicle or maybe a truck or maybe an airliner or a stealth bomber。

All of these solve the problem of getting from one place to another。In the same way。

 let's think about several different ways to solve a programming problem。

 you can use C or Java or MATLb or C++ or Python， Ruby， OcaMl， there's many。

 many different ways to solve a programming problem。And of course。

 the parallel here is to emphasize the idea that different languages are appropriate for different tasks。

 and we'll try to talk about that in the context of each of these languages。Now just to start。

 hopefully after this course you can write Java code and just as a running example。

 we'll use the three sum program that we studied in the performance lecture。

 where what we wanted to do was read a set of integer values from standard input and find all the triples at sum to zero and this is code from our lecture on performance。

We take an integer n from the command line， we make an array to hold that many integers。

 we read those integers off standard in， and then we go in a triple4 loop checking all the triples of those integers to see if they sum to zero。

And we print out the ones that do。And that's a program that we' studied。

 we're just going to use that as an example and so if we have a file called8 ins text that has those eight integers。

 30 minus 30 minus 20 minus 10， so forth。We compile our program with Javac3 sum。 Javava。

 and then we run it by typing Java 3 sum and we give it the command line8 and we take from standard input 8 inch。

text， then it prints out those four triples that sum to zero。So you can write this program。

 if we were to give you a similar task， you could write a program to do it and give it data as input。

 compile it and run it and solve the problem。And so now I want to tell you that well knowing that you can also write C code。

 there's differences and the differences are highlighted in red here and I'll talk about them briefly。

 but even not understanding quite what those things do， you can pattern match off this program。

 much in the same way when we first started there were things in hello Jahava you didn't understand。

 but you still were able to write that program and run it the same way you can do that with a C program。

So that's the text of the program it's got those differences highlighted in red and for the same file if you typecc3 sum。

C， your computer most likely has a C compiler， that's what CC stands for it produces a machine language file called A dot out。

 always produces the same file A dot out， if you want to save it away in 3 sum dot machine language or whatever you can do that。

And so to run it， you type8 do out， give it a command line argument and this is and take its command line from its standard input from the file。

 same as before， and it'll print out those same four values。There's lots of noticeable differences。

 so first thing is and the first two is the library conventions。

 how do I specify where the standard input in other libraries are and that's using the include statement with the library names or dot H and they're inside brackets and C。

The way that we create arrays， there's the second line of the program， in star A。

 you've got to have that star equals Malik n star size of in that says give me an array of n integers at execution time。

Standard input， we say scanF in C， and then there has to be that all important ampersand before the thing that we read and you can learn about the details of all of these things。

 and then also taking from the command line A2I is a function that converts from string or ASII2 integer。

The star in the Amperserson have to do with pointer manipulation and we'll talk about that in part two of the course。

 but those are the highlighted differences， but even so from this program。

 you can write another program that reads in integers and processes it in some other way the body of the program is very much the same as it was in Java so you can write see if you've always wanted to write a C program type in this one and run it and then maybe write another C program。

The big difference between C and Java and there are plenty of differences is that there's no data abstraction。

 there's no objects in C， a C program is just a set of static methods。

 the way Java was before the last couple of lectures where we talked about data abstraction in objects。

In 1989， Bjorn Straustrop introduced C plus plus and the idea of that。

Language is to add data abstraction to C。It was calledC with classes。

 and it embodies many of the ideas of object oriented programming that were coming into widespread use。

 and that was the purpose of the C++ language。You might remember this quote from Strstrip。

There's only two kinds of programming languages， those that people always gripe about。

 and those that nobody uses。So you can also write C+ plus code Well。

 one thing is that you can use C++ pretty much just like C now there's differences。

 so now we have a more friendly way to create an array。

 more like we're familiar with in Java new int and in brackets。

 the body of the code is pretty much the same。 the input and output are different and we'll talk about that in just a second。

You likely have a C++ compiler on your computer， you should call the program。

cxx for c++ cP is the name of the compiler， so if you type CPP3 sum。 cxX。

 again it creates an8 do out， you run that8 out out with the right command line argument in the file。

 you get the same four output。Though very similar to see the differences again。

 the libraries or a little bit are named differently。

 standard input has this idiom where we use double greater than signs it's kind of like pushing it to getting it from an input stream and the output idioms the same way double less than signs getting it from the output screen and it's not formatted which many people found annoying and nowadays you have formatted printing in C++。

 but it's also got this pointer manipulation， that's what the star and the A has to do with and we'll talk more about that in part2。

So you can use C++ with objects and this example is from a program in Part two calledBuilding a symbol table with binary search trees so we won't really do the details other than to show kind of the idea of an object that contains fields very much the same way that we write it in Java。

 this code is actually from a version of my algorithms book in 1990 that code still works fine today。

 C++ is very widely used throughout our computational infrastructure because it combine the simplicity at C with the power of object oriented programming。

Now， the big challenge with C++ is the idea of pointer manipulation。

 and that that algorithms book talks quite a bit about that。

 We're manipulating references to objects directly in our code。Also the idea of generics。

 which we talk about again a little bit more in part two。

 where we want to write programs that can work with any type of data。

 that's something that was bolted on to C++ later in the game， so that's a challenge there。

 it's also a challenge in Java to be frank。But the big difference between C and C++ and Java。

 and again， there's many， but the big one is that you're responsible for allocating memory in those languages。

Your programs can manipulate and do manipulate pointers。

 the system has a library of methods that will do memory allocation and reserve memory for you。

 but programs explicitly call methods that get memory called allocate it and free it for any objects that are created。

And this creates a big possible source of bugs called memory leaks。So if you have C code。

 you want to reuse an array name， so you create the array with a。

Call to a memory allocation routine and this says get me five doubles。

 and then when you're done with the E free the array。

 and then maybe you create you get another one with 10 doubles， for example。In Java。

 we have automatic garbage collection where the system keeps track of all references。

 manages the memory use， reclaims memory that's no longer accessible from your program。

 and the programmer is freed from dealing with it。So in Java。

 you just say give me an array of five doubles and then sometime later。

 give me a new array of 10 doubles and that first array of five doubles。

 the system goes and reclaims that memory at some point。Like many people。

 I I personally and many others dragged kicking and screaming into this because it seemed to us that garbage collection was going to be very slow and inefficient。

It's turned out that actually the cost of garbage collection is hardly noticeable nowadays。

 and it's much， much better for programmers， particularly beginning programmers to not have to worry about where the memory is。

And even an experienced C programmer might forget or make a mistake in the amount of memory freed。

 which can lead to crashes and that's certainly one source of crashes in modern systems is memory leaks where the programmer loses track of the amount of memory being used and eventually the system runs out of memory。

 so that if you want to learn those languages you're going to have to learn to deal with memory allocation。

So just in general， if you have code that manipulates pointers。

 it's much more difficult for this system to check that the codes free of that sort of bug。Okay。

 what about Python， A lot of people ask us， why don't we teach the course in Python？

And well as take a look at Python， you can certainly write Python programs。

 one thing that you can do is use it like a calculator。

So most likely on your system if you type Python you'll get access to an interactive version of Python and it gives you three greater than signs and then you can type expressions at it I if somebody says that's what I have I type  two plus2 and it gives me four so I'm happy with that next thing I do is well let's compute the golden ratio and figure the square root function must be called SqRT and always it says well I don't know what square root means so I have to go and look up and find out how to import the math library so not so difficult type import math and now I can type any math expression and I get the golden ratio so just with that much and you can there's online documentation type help there's lots you can do within just a few minutes or a few hours you can throw away your calculator please throw away your。

because you can write code and save code and get extensible libraries and all the benefits of programming on any device that runs Python。

 and that's pretty much any computing device that you might have。

But you can also use Python like Java。 and we can write our three sum program。

 Here's the Three sum program in Python。So and I'll talk about all these differences in a minute。

So for Python， you just say Python， type in that program， say that program name。

 command line argument， the standard input redirection， you get the answer right away。

So the noticeable difference are number one， you probably notice there's no braces。

 one thing people dislike about languages like Java NC is the braces。

 the left and right braces that seem to be all over the place， Python in dense mean braces。

 you can indent you have to be consistent in some Python programs insist that you indent a certain number。

 but in this program each indent just means a different block of code。

 we actually have there's no two line blocks on this program。

 but if you had two lines the same indentation to just be like braces around those。

Another quite noticeable difference is there's no type declarations。

We never said that N was an integer or that A was an array of integers。

Python has what's called runtime type checking， and we'll talk about that later on。

 works okay as long as when it comes time to assign a value to the thing that the one that you're assigning it happens to be an integer and we'll talk about that later。

Ray creation is always different， so Python， you say zero on bracket star n makes an array of n zeros。

The Iioidioms are different， so stand Iio read in。So that's our standard IO library。

 You could also use Python's Ss Stan in model。They have a built in print or we have a standard IO IO。

 even for simple taking from standard input standard output stream is always something that you have to cope with in a new programming language。

 one of the first things that you need to know how to do， but again。

 you can take one of our sample programs and get pretty far once you've seen how it works for one sample program。

The other thing about Python is the for loop works differently。

 so we say for I in range in range of an integer is a a list from zero to that integer and it's a way of specifying all the possible values that I might take on there's pluses of minuses to that approach that we won't get into right now but that's how you can decode this program and how you can write Python code。

 so with this right away again run this program if you've always wanted to run a Python program and then modify it to do something else with integers and you're often going with Python programming。

It does bring up an important concept that we've talked a little bit about。

 but in the context of Python is a good time to really make this distinction。

So with Java we've been working with a compiler which takes your whole program and translates it to machine code。

 actually in Java case it's a virtual lowlevel language that later is translated to specific code for specific machines so you have your source code which is the text that you type and you type Java C and this program called the compiler converts it into machine code and C and C++ do the same kind of thing。

An interpreter is a different kind of program。 What that one does is simulate the operation of a machine running your code。

So in fact， that's what the Java virtual machine does when you say Java takes this simple machine code and it pretends that it's your computer running it。

C actually makes machine code and just runs it in C++。

But for Python what Python does when you say Python is it runs this program called an interpreter that takes your program one instruction at a time and executes it keeps track of the values of the variables and changes them according to what the program said it does it one instruction at a time it's a bit slower to do that because there's a lot of work looking at the meaning of variables and so forth but on the other hand it's just a different computational experience it's kind of closer to when you had the interactive python you type one instruction at a time。

 it's the same process that's going on when you put your instructions in a file and run them。

Now one big difference between Python and these other languages again there's many is if Python doesn't type check and compile time。

 so that's why there's no need to declare types of variables。

 the system only checks for type errors at runtime when it's time to assign double value to a variable。

 and then maybe add another double value to it it's only at the time that those operations are performed on those types of data that the system checks to make sure that it can do the operation that's specified。

Now it does make it easier to write small programs。

 you have an idea what the type of your variables are in the idea is you shouldn't have to continually remind the system that I'm working with an integer。

 I know I'm working with an integer on the other hand。

 for large programs with complicated objects with types with behavior that we're building this is maybe questionable at best。

And here's a typical scenario of that I've heard now more than once in the real world。

 that's a combination of this idea of no compile time type checking and the idea that Python is interpreted。

 so a scientist or a program will use Python to solve a small program because it's so easy you just type it in there's no braces。

 but small programs have ways of turning into bigger and bigger programs。

And maybe at the time that it's actually seems to be debugged and we're ready to run it on big data。

 the scientist or the programmer makes a mistake， maybe near the end of the program。

 maybe the name of the file where the results finally get written is supposed to be a string concatenated with something and it's not quite the right type。

So what might happen is that first of all the program runs for a long time because you can debug it for a small problem。

 but when you give it a big problem， you're going to notice that Python's a lot slower than Java so rather than your thing finishing in a half an hour it might take half a day or more and then it crashes because gets to the type error and just crashes and have heard of this happening in more than one situation in the real world。

 so what I say is that using Python for large problems is playing with fire and I'll come back to that but it is reasonable to number one。

 throw out your calculator and use Python and number two it's fine to run prototype in Python but if you're going to take this program and use it for some scientific investigation or some product that you want to sell。

 you really want the benefit。of the kind of automatic checking that a system like Java does。

 and also you might want the efficiency that you get from compile code as opposed to interpreted code。

And then there's MATLb， lots of scientists and engineers use MATLb and you can write MATlab code again just here's another language just like Java。

 so now our four loops， we say one colon N to mean from one through n in the race start at one not at zero。

 of course the input output is different， we don't have braces but we have to type end at the end of blocks。

 so all of these things are easy to deal with and now that you've seen this program。

 you can write MATLb programs to do tasks just like with the other ones。

Always wanted to write a MATlab program， go ahead and write code like this。

 The more typical example in what it was builted for is to use MATLb for matrix processing。

So if I type this code， a equals squareb 13，5， semicol and 247。

 I'm specifying a matrix with two rows and three columns。And then if I type B。

 minus 58 semicolon 39 semicolon 4 is0， that's a matrix with three rows and two columns and then I can just type C equals a times B。

 and that means matrix multiplication in MATLb and then if I just ask for the value of C。

 I get the multiplied matrix。And of course， it can do eigenvalues and many other things。

 so using MatTlab for matrix processing， that's definitely what it was builted for。

 it also has powerful tools for making graphs and plotting and doing other things。

But the big difference is between MatTlab and the other languages we've talked about again there's a lot。

 The first one is MatTlab is not free， so I notice I didn't say you can just go to your computer and type MATlab you have to buy MatTlab or your institution has to buy it And if you write code for MatTlab and you want your family to see your code or whatever they're going to have to buy it that's why we don't use it in beginning course And the other thing is that most MatTlab programmers really just use one data type the matrix and they kind of understand that that's what they're doing for example。

 a MatTlab， if you say I equals zero。Well， what that means is redefine the value of the complex number I to be a one by one matrix whose entry is zero。

 probably not what you intended， again， no type checking and all kinds of concurrent problems。Now。

 it's important to note that MatLb happens to be actually written in Java。

 it's intended to process some matrices in a more general task。 that's what Java is intended for。

And actually， Java compilers are written in C， nowadays C compilers are written in C and really that's really the right way to build a programming language。

 at least test it by writing a compiler in that language。And there's good matrix libraries。

 actually a lot of times the same matrix libraries are available for all these different languages。

 so you can do matrix processing in any one of these languages。

 it might not be quite as simple as a times B as it is in MA lab。

 but you can even make it that way in say， C++ or Python。



![](img/3c9f190028ffded25cebf345c68aec83_2.png)

So it's certainly reasonable to use MATLb as a matrix calculator。

 but if you want to do anything else， probably you want to use Java C or C to C plus plus actually nowadays。

 you can get matrix calculator on your phone。So now you know how to program in lots of different programming languages。

 C， C+ plus Python， MATLb， there are lots of differences。

 might take some study but not nearly as much as you might have anticipated before you learned how to program well in one language and most computer scientists will say that learning the first languages what's important。

 and you're going to learn many languages if you're involved with computers。



![](img/3c9f190028ffded25cebf345c68aec83_4.png)