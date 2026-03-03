# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p15 7_04_01_第4章函数与程序结构的历史背景-第2部分.zh_en -BV1v2421P7pt_p15-

![](img/27eefec4b51a69598891e517bc612ed2_0.png)

A recursion， recursion， recursion， recursion。When a function calls itself， it's called recursion。

 it's a powerful， it's a beautiful concept， there is places when if you're given a tree like structure like you parse some XML or something and you're reading through the XML。

 recursion is such a pretty way to write code。I'm about to show you a very simple recursion example that are two things。

 First， they're really inefficient and silly uses of recursion。

 and they mislead you as to why you should use recursion。

 and they misleadingly kind of tell you that like recursion is great。

 Let's use it for something it doesn't is not well used for。So so really in this section。

 I'm not trying to show you。What recursion is used for Well。

 I'm more interested in giving you a really。Artificial synthetic example to show how the call stack works and how recursion works with the call stack。

So here we have。I mean some tortured code， it is not pretty code。

This is a I'm writing code that if given a number like three。



![](img/27eefec4b51a69598891e517bc612ed2_2.png)

Adds up 1 plus 2 plus 3。Okay， and gives me6。 There are so many ways to do this。

 There's even a closed form solution that doesn't even require a loop that's called algebra。

But we're going to use recursion。So。If you look at the int main， I'm going to say sum up 3。

 That means sum up things 1，2，3。So sum up is being called from Maine。

 and then I've got the return value， and I saysup， and you'll notice in the printout that sup is the very last thing it comes out。



![](img/27eefec4b51a69598891e517bc612ed2_4.png)

And so if you。Walk through， sum up。

![](img/27eefec4b51a69598891e517bc612ed2_6.png)

You see that there is a parameter called above。That's coming。

 I call that above because it's coming from whoever's calling us。 There's a parameter below。

 which is we're going to compute a value and send it down to the next copy of ourselves down。

 and then sum is the sum of the the above value and the sum of the below values。 and then Re Val is。

 I mean， actually sum is just coming back from the call to ourselves。

 And then RE Val is adding those two things together。

And I do this in exceedingly slow motion with print statements everywhere that just makes us look ugly because really the only thing that matters is where it says sum equals sum up below。

 and what we're doing is we're calling the same function again。

So if you look in Maine and you see the sum up call， that is going to create a stack frame。

And in that stack frame， it's going to have a whatever the three number is。

 we're going to make an above variable， copy 3 into the above variable and allocate it below sum and Re valve。

 So our stack frame is going to have four integers on it。And then the function starts working。

And the way the rate recursion works is there's always got to be a time at which it stops。

 This is kind of like going down， down， down and then has to work its way back up。

 If it goes down forever， that's called a stack overflow and then your computer runs out of memory and your application blows up so。



![](img/27eefec4b51a69598891e517bc612ed2_8.png)

You have to have a time at which the stack algorithm stops。



![](img/27eefec4b51a69598891e517bc612ed2_10.png)

So what we're saying is if we're being told to sum up one or less， well。

 we define the sum of that as one， so we just return the sum of everything up to one as one。

 and that's our way of stopping the recursion at the bottom。

And then what we do is we take below and we subtract one from it。

 so if we're being called with three， below becomes two and so you see that over in the lower stack frame。

 below is two。Right below is two and we're about to go down deeper into the call tree。

 And so we're going to call sum equals sum up below。

 So what happens now is we're passing two in to another stack frame。

 And so there's not really a another copy of the code， but there's another stack frame。

 And so now we're calling sum up with two is the parameter。 That's our below。

 but then we see the stack frame。 and now this is the stack frame that's kind of on the left hand side there above in this stack frame is2。

And then execution begins， and we subtract one from below。 Well， above is not less than one。

 So we subtract one and above below becomes one because it's2 minus-1。 And we're going to go down。

 So it says down one， which means it's going to again say sum equals sum up below。

 and below in this case is one。And so it makes another stack frame's so we're actually there is a maximum of like three calls here and then it's going to work its way out。

 So then it calls another stack frame that's not shown on the right-hand side。

 and then it runs with one as above and then above is less than or equal to1 so it returns one and that's why it says in one and it doesn't say anything because then it's returned and it returns the value1。

 So now the third stack frame comes off。And now we're in the other stack frame and sum is what the return value of the sum up call was。

 so it says back one。And then it says above now we're in the stack frame。

 that's on the right hand side， so sum is one below is one above is2， and so we compute rat valve。

 which is one plus2 and that's3。 and we print that out and that's kind of where where we're indicating and then we return the three。

Right。And then it returns rat valve and it runs some more， it gets three back than it。



![](img/27eefec4b51a69598891e517bc612ed2_12.png)

adds the three to it and returns one more time and the stack all pops up and eventually you get six。

And this is a， I mean， you can look at this as long as you like。

I don't this code is like a foolish way to make this calculation like most。

Artificial recursion examples。 the key thing here is just think about the stack frame。

 right every time you call in another stack frame happens。Call in stack frame happens。

 and then when the return value happens， it goes back to that stack frame。

 so the stack frame is a way of pausing execution at the moment， create a new stack frame。

 executing in that stack frame， and if you need to have a yet another stack frame。

And so this idea of creating stack frame with the parameters and automatic variables each time you call a function。

 copying the parameters into that stack frame， and then executing the function in that stack frame。

 we're not making extra copies of the function， we are just creating a new stack frame。

That's what the essence of recursion is， is the fact that you have a stack and each call makes a stack frame。

 and if you recursively call again， you just make another stack frame。

And so it's almost easier in my mind to think through how stack frames work than it is to think through how recursive code works。

Now I want to talk a little bit about the C preprocessor。

It's the last thing of this chapter and it's in some ways orthogonal to functions in program structure。

 I mean， it is part of program structure。And so I've talked a lot about how wonderfully the C compiler。

And eventually UniX solve so many problems of software source code portability。

And things like indianness and character arrays and。

Masking is shifting not being necessary that those were awesome。

 but the problem was is that C has always operated in an environment。The language has changed。

In the early days， it wasn't standardized by 84。 it got standardized。

 NCC came out A lot of people used it outside its original creation and so a lot of things got fixed in the first decade of Cs used the language evolved a lot The language kept evolving and a lot of the things that would make it evolve are things like integers went from 32 bits in some situations to 64 bits and then you have to say well。

 what is a long as long 64 long 32 because it started with int being 16 bits and long being 32 and then long with 64 well for a while then ints were 32 and longs were 32 and then ints were 32 and longs were 64 and what would happen if ints were 64 and it had to do with computer architecture 64 bits right？

And so sometimes you would have a bit of code and it just。

You knew you wanted a 32 bit thing and you weren't sure if an int or long or a short was going to give you 32。

 And so you had to say you know I really need different source code Like if I'm working on a PDP 11 I got one thing and if I'm working inter data 7。

32 I want another thing because really I want 3 a 32 B integer and now there's actually int32 in some of these things because you do need to know sometimes you're using 32 bit integer then librariess changed there's calling sequences that changed because again。

 as computers got bigger and bigger and memory got bigger and de drives got bigger。

You would be in a certain version of an operating system and the calls to reading files might be slightly different。

And so it's not really that the source code was portable。

 it's the calling sequences to library started to change hardware evolved， operating systems evolved。

 C started running on non-uns because C originally started on Unix but then it quickly went to other operating systems because it was such a powerful concept。

 but sometimes in these other operating systems。Just things were kind of different because they weren't working on Unix。

 and so the preprocessor really was a。An effective a way to patch your source code so that you could say。

 look， I wrote this source code 10 years ago and it worked on a PDP 11 and now I'm going to run this on an IBM 360 architecture and I don't want to change that there's a few changes I need to make。

That have nothing to do with sort of the what what a for loop looks like。

 But it has to do with like what library I'm calling or what the return type for that library might be。

 So the pre processor allowed us to put。Variations in the source code and the preprocessor。

 it really feels weird because it its syntax syntax is very different because the preprocessor is kind of a line oriented processoror。

 and it has these pound things these like pound if def pound defined pound L。

 pound end if and pound include。 that's even a preprocessor。

 So at the preprocessor is is a not a compiler at all。 it is a source code to source code translator。

 it expands the include files。 and then it makes changes。

 So in the top example where you see pound include STd do H。

 you can actually run Gcc minus capital E， and says just run the preprocessor and shows me what comes out。

 You take you know 1012 lines of code on the left。 and it puts out hundreds and hundreds of lines of code on the right。

 I'm only showing you a subset of it。 But the biggest part is the fact that include STD do H is literally expanded。

 And then that is C code with。

![](img/27eefec4b51a69598891e517bc612ed2_14.png)

![](img/27eefec4b51a69598891e517bc612ed2_15.png)

Out the pound include。

![](img/27eefec4b51a69598891e517bc612ed2_17.png)

Okay， so that's the preprocessor， but then another example here is I'm creating this。

Use underscore long。 This is not really a variable。 This is a compiled time variable。

 So I'm going to create a new string called int underscore 32。 and if use long has been defined。

 I'm going to make int32 be long else。 I'm going to make int_ 32 be an int。 and again。

 this could be a thing where I'm compiling for different architectures。

 and I want this variable IP address to be a 32 bit integer。

 and I need it to work on different operating systems。So in this case。

 because Use long is not defined int 32 as a string substitution。

 like a macro string substitution before the compiler even does anything， turns in32 into int。

And so that's what the five lines of pound if de and all that stuff do is it says。

 change this int 32 string in my source code into int。

 And so what we see on the right is really C code。 What we see on the left is kind of。

C preprocessor plus C code， and so the preprocessor transforms source code to source code。

So I was looking around some old code that I happened to have grabbed and put into Github。

 which was some code from 1994 from Xmosaic 1。2 and for those of you took my Internet history technology and security。

 you know that Xmosaic was the first web browser that was portable across multiple operating systems and the more and then eventually mosaic ended up on Uniix systemss with X windows。

 that's what it's called Xmosaic and it went to the Mac and went to the PC and so it was really many Uniix's Mac and PC and what we're seeing here on the right-hand side is actual source code from that which was written in like 1993- 1994 and what you see as a bunch of if Ds ifN Defs and some comments and there's a ifDes。

 Soeris 9 broken and it has to do with like where do we find the error messages across all these weird operating systems because the way they put error messages sometimes they would use Xtern。



![](img/27eefec4b51a69598891e517bc612ed2_19.png)

Which are global variables defined inside the runtime。 And we would just look at those variables。

 We would make a function call， and it would write into these global variables。

 But then that global variable might be different。 So this is actually from some code that was H Tt。

P and C。

![](img/27eefec4b51a69598891e517bc612ed2_21.png)

That was some early network connections。 Now these days， you know。

 we just do this stuff in like the pound import requests in Python， but in those days。

 the C libraries for network connections were really different， meaning that they were just。

 you know， here comes the network， Here's this language C。 It's been around by you know， 89，9091。

wereThe network was there and so we were building libraries。

 but then how each library worked in each operating system was a little wonky。

 and so they had to write different C code to compensate for the different operating systems that this C program a web browser would be running on。

And so all these if defs mean that one source code with a few predefined。

Consts compile time constants could then work on a wide range of operating systems， and so yes。

 the sea language itself is portable， but we also want to be portable over time。



![](img/27eefec4b51a69598891e517bc612ed2_23.png)

And so sometimes libraries change， operating systems change。

 and we want to be able to compensate for that。 and so this is an important part to see these days it's less important because a lot of the libraries have stabilized and they don't change quite so much and so this code here would probably just be a bit of socket code and the errors would come back the same way。

 no matter what version like。🎼VMS is an operating system that doesn't exist anymore。

 thinks C doesn't exist anymore。 Next doesn't exist anymore。 Ceris doesn't exist anymore。

 So these are all operating systems don't even exist anymore but this code was portable across all those things。

 and actually I compiled all this and you can kind of take a look at it。

 I made a video where I resurrected this code。 it's got to be eight or nine years ago on a Macintosh。

 which is evolved from next。 I don't know if I could get it to work again。

 but back then I got it to work on a Macintosh and I said to find it as next。

 And so I compiled the C code。

![](img/27eefec4b51a69598891e517bc612ed2_25.png)

And there is't X windows on Macintosh， I got the X Windows library。

 I got all this stuff work and I told it， you're anex and then recompiled the C code and eventually something came up and I made a video about it and so on because I knew that it could be very difficult to keep this thing working over time but to go from 1994 to 2014 and recomped something in you 20 years later that's still pretty impressive that that next code would still work things like the VM code。

 VMS code that there's no VMS computers that I know of these days。



![](img/27eefec4b51a69598891e517bc612ed2_27.png)

So it just it just shows that。The idea of you know portability。Is a。

Some of it is simple and elegant and was laid down in 1978。

 but then there are things outside the programming language that were evolving and still are evolving to this day and if you are doing C coding today or C++ coding today。

 you may be using things that start with Pounine which are compiler directives rather than C code So with that dive into chapter4 and learn about functions。



![](img/27eefec4b51a69598891e517bc612ed2_29.png)

Yeah。

![](img/27eefec4b51a69598891e517bc612ed2_31.png)