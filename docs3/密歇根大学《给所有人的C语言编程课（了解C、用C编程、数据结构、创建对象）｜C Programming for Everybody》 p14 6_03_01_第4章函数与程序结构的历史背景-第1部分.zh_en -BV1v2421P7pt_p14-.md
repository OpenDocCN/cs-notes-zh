# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p14 6_03_01_第4章函数与程序结构的历史背景-第1部分.zh_en -BV1v2421P7pt_p14-

![](img/8b22935435c47c79053123a5a37e94b6_0.png)

Welcome to Chapter 4， Funs and program structureuc。In this chapter。

 we're going to start digging a little deeper。 Part of the goal of this course is to get you to the point where we can talk about how things really work Eventually in the next course。

 we'll even go down to hardware， hardware and architecture and gates。

And so it's time to start opening things up and looking at how things work。

And so this is a good time to do so and the big thing we're going to learn among other things is the concept of a stack。

How passed by reference works， how passed by value and pass by reference work。

 a little bit about recursion， recursion is a thing that I worry about a lot。Well。

 we'll get there and a preprocess， these are all things where we're really starting I'm not it's not so much about just how functions work。

 but how functions are implemented and how that affects how they work。

So the first thing I want to talk to you about is a really nifty computer science concept called a stack。



![](img/8b22935435c47c79053123a5a37e94b6_2.png)

A stack is a data structure that。We use， and it has a couple of attributes。

 The idea of a stack is we we start with an empty stack and we put things on the stack and then we take things off and we take them off。

 The last thing we took put on is the first thing we get off and they go up and they go down。

 You can push things on them and take things off of them。We can approximate this with a Python list。

 so we start with an empty list。 We append the string one to it， and the stack has a one on it。

 It's kind of growing up from the bottom and it's going to shrink from the top。

 And then we append a two to it。 and then we our stack is now one and2。

 So the bottom thing in the stack is one and the top one is two。 and then we append a three to it。

 and we have one，2，3 on the stack at that point。 we pop。

 pop says give me the most recent pushed thing and then take it off。

 So we pop off three and the stack remains with one and2。 Again。

 this is also known as the last in first out or life O Q a Q is like a line of things。

 And so the last thing in is the first thing you got out。

 So that's a stack and we're going to use stacks in function calls。So historically。

 when we talk about call by value and call by reference。

 we basically say that call by value means that somehow this value。

 like in the main program M with a variable with a value 42 ends up being copied into the function。

 and the parameter O is has got a copy of the 42。 It's not the original MA。 It's the copy of 42。

 So 42 gets passed in the function 1， and O is a copy of 42。 So then inside the function。

 we can subtract 10 from it。 and then。We can see that。

 but then when we get back in the main function。 We see that M A has been unchanged。 And it's like。

 oh， we build a little wall around the function and nothing inside the function happens。

 The outside world is unaffected by it。 And that's a great oversimplification of call by value。

 Of course， call by reference means the stuff you this function can affect outside the function。

 But let's talk a little bit about how a stack is used to accomplish this。



![](img/8b22935435c47c79053123a5a37e94b6_4.png)

So just to use some terminology。C calls these variables that are allocated inside the function before the function starts as the automatic variables。



![](img/8b22935435c47c79053123a5a37e94b6_6.png)

And frankly， intma equals 42 in main is an automatic variable inside the main because main is a function inside a C program that happens to be the one that starts everything out。

So if we get to the point where it says int ma equals 42 and then it prints MA。

Being 42 at that point on the stack， the C run time is allocated one integer。

 and we've assigned 42 to it。 So that's what the stack looks like at that first print statement in Ma。

 Then we call the function 1 and pass M A N。And this is where the C runtime library， kind of before。

Everything starts out in the function 1， it allocates what's called a stack frame。

And a stack frame includes the parameters， O P and the automatic variables that are inside of that function。

 And so in this case， we're going to get two variables。

 We're going to get O P as an integer and T N as an integer。 and before the program starts up。

 the value 42 is copied。From MA A and O P。And so the stack frame is the context in which that function operates。

 So when it first starts， you see that O has 42， you also see we have two copies of the number 42 and we have a parameter O。

 and then we have the automatic variable， the TN。Then the next line runs。and at that point。

 O is changed， O equals O minus Tn。And so O becomes 32。

 But you'll notice that on the stack beyond the stack frame。

 the stack frame is our current execution of the function 1 beyond the stack frame。

 the 42 is still there。 we can't see it we're in the function right now and we're only seeing the top part of the stack We're not seeing the part of the stack that belongs to the main program。

 So that's where it prints out 32 So 32 in the function says O is 32。 and that's fine。

 And then we return， and that's when the C runtime removes the stack frame pops those things off the stack。

 It remembers how much it put on， and it pops all the stuff off the stack that it put on and then it' basically comes back into ma and the stack frame for the main program has one variable in it and it's MA and it has 42。

 And that's because one operated in its stack frame and now the main program is back to operating in the same stack frame。

 you can almost think of this as like。

![](img/8b22935435c47c79053123a5a37e94b6_8.png)

![](img/8b22935435c47c79053123a5a37e94b6_9.png)

One never happened， right， from Ma's perspective， it had some variables。



![](img/8b22935435c47c79053123a5a37e94b6_11.png)

One ran and a stack frame was created。 Some of the main data was copied into the one stack frame。

 one operated in its stack frame， and then the stack frame went away right before one or right at the moment that one returned。

 and the return value ends up in the stack frame too。 I just haven't shown you that。

 And these don't return value。 the return value comes back from the stack frame。

 But you can see how main started with the stack with one one variable on it。

 and then one ran and all that stuff happened， and then it kind of was undone。

 And that's where the changed variable just kind of went away。

 And so the stack it's as if nothing ever happened except it went up。 and then it went back down。



![](img/8b22935435c47c79053123a5a37e94b6_13.png)

Now one thing we notice in Python， we see this too where you say everything is called by value which implies a copy。

 except for things like certain objects and calling methods and objects。

But if you look at say this function Zap and we pass in X， and x is starts out as original。

 and then it calls the Zap function and it passes in and it's got the original。

 then it gets changed inside the Zap function and that change prints out。

 but then when it comes back。It is back to the original。

 so x is back to the original in the main code， and you might say， oh， that looks right。

 and that's actually quite intuitive and that Python has made it so a call by value inside of this call by value to the Zap function。

 it happened， meaning that nothing change nothing changed outside of the Zap function。

 and it was a call by value， not a call by reference now。

I'm not going to go into it at least not right now talking about why that really worked。

 and it's less about call by value and call by reference and more about the fact that y is really a pointer to an object and when y equals changed executes inside of Zap。

 the object pointer， it points to a different object and then but x never changed and so。😡。



![](img/8b22935435c47c79053123a5a37e94b6_15.png)

Python has a slightly different runtime， but it leads to this notion that seems like a string variable。

In Python is called by value。Now， if we look at the similar but quite different code inside of C。

We see the main has a character array X of unknown length， which is original。

 and that just unknown length means that it it looks like eight characters plus a back slash0。

 which is nine characters， and it prints out kind of like a string。

 It's a character array with a terminator， and then we call Zap pass X in。



![](img/8b22935435c47c79053123a5a37e94b6_17.png)

And then inside of Zap， Zap takes a。Character array as its parameter。

 and it can print out the word original when it starts， and then it copies changed into it。

And then it says at the end why is at the end is changed。

 but then we come back and back in the main program， it got changed。

So does that mean it was called by reference or what？And the answer is sort of。

 and this is where it kind of helps。So it turns out that when you are passing an array。

Into a function in C。You're not actually passing the contents of the array。

So most time we think of that 42 being copied if it's an integer。

 if it's just like a scalar thing like a float or an enter cha or something that's being copied。

 but when you have an array that could be gigantic。

 so it doesn't actually copy in the whole array so when X is being passed into Zap and being received as y we're not actually passing the string because that could be a million characters for all we know。

 so it's not like it makes an extra copy of a million characters。



![](img/8b22935435c47c79053123a5a37e94b6_19.png)

What is doing is its passing in the address of the start of the string， not on the stack。

 but somewhere else。It actually could be on the stack somewhere。

 but it's not in the stack frame and the word original is not copied。Into the stack frame。

 the stack frame only includes a pointer or the address。 X is the address of the letter O。

 and then Y is also the address of the letter O， which means when we're calling stir copy。

 we are overriding those characters。 Oh， and by the way。

 I carefully made sure that the string changed was shorter than the string original。

 or my program could have blown up because this is C and arrays don't get bigger。



![](img/8b22935435c47c79053123a5a37e94b6_21.png)

Python strings get bigger， but arrays don't in a couple more lectures。

 We will build a data structure where it's like a Python string， and we can add to it。

 and you'll see that the code is very complex。

![](img/8b22935435c47c79053123a5a37e94b6_23.png)

A character array is very simple。It's not exactly a pass by reference。 It is a pass by location。

 And if you happen to misuse that location， meaning you write to that location。

 you write to location。 Now， this might have been in like read only memory something。

 your program might have blown up， so。You better be sure what you're doing when you start messing inside of a function with an array that's been passed to you now sometimes you're supposed to sometimes we tell you to write that。

🎼Another thing that you're going to see in this is the reference to register variables。

 this is another rather historical notion and in my opinion it really had to do with convincing really skilled assembly language programmers that they could get the same performance out of C that they were used to getting inside assembly language and so what a registers well。

When you have a central processing unit and you have memory。

 the data lives in the memory and the registers live in the central processing unit and depending on the speed of things。

 a register might be you know 40 times faster than regular memory and so if you could keep a variable like I。

🎼In a loop， you could keep that in a register that's faster。

 And so what we can do with saying register in X is say， hey， by the way， the next few lines。

 X is a really important variable I expect to use it a lot。

 so if you can possibly not store this in memory， please do so。

 and that's why the only kind of weird thing about the registers you can't get the memory address of a register variable。

Now Mon compile compilers， we have runtime optimizers that are miraculous， I mean， they border onrac。

 even the simplest of runtime optimizers that speed the code up at runtime are miraculous and。

Saying this is a register that's a register might actually confuse things so all the register does is hey I am never going to ask you the address of this variable so don't bother putting it in memory if you don't feel like it。



![](img/8b22935435c47c79053123a5a37e94b6_25.png)

And so it's probably， but I also think it's kind of fascinating and fun to think about this。

 think about how early see developers were so deeply connected to their assembly language that is at the runtime。

So。🎼Yeah。

![](img/8b22935435c47c79053123a5a37e94b6_27.png)

Yeah。