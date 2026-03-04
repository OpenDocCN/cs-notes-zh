# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p07 6_08_optional-very-high-level-outline -BV1bw4m1D7MM_p7-

The last topic I want to cover in the introductory material before we really start the course and start on this amazing journey is just a highlevel outline of where we're going。

 And I want this to be optional because first of all。

 it's fine to just start and see where we're going as we get there。

 but also because there's no way to discuss the course in just a few minutes without using a bunch of jargon and terminology that I don't expect you to know yet。

 the whole point of taking the course is so that you learn about these things and I would hate for you to watch this video think I have no idea what he's talking about。

 I guess I shouldn't continue on and that's exactly why you should continue on so that you can learn about all these things that will explain one piece at a time。

😊。

![](img/3b79461de4a2e26a7c942013bce5d45b_1.png)

With that said， let's kind of give the overview in case you've seen some of these things before and want to know。

 am I going to get to some new stuff or I've heard。

 I really want to learn about something is that going to come up。

 I'm certainly not going to list every topic here you'll be able there's just too many there's many weeks worth of stuff but at a very high level here in part a of the course we're going to do the basics of functional programming in a statically typed language。

 namely M。 So we're going to start with basics， things like variables and scope and numbers and addition don't worry。

 of course you've seen that before when you've programmed before。

 but we're going to do it in a precise way。 we'll build up to functions which are like methods but without objects if you've seen object oriented programming。

 we're going to do recursion， In fact it's the way we're going to write iterative computations as well as other computations。

 we're going to have ways to build larger data structures both tuples and lists。

 that's all going to be in section1 So with that and the software installation stuff。

It it's a fair amount， especially in an unusual environment， so we give extra time。

 that's really like you have about twice as long for that section as for the ones that follow。

After that section2 is all about data types and pattern matching。

 this is a new way that most of you probably have not seen before to represent larger data structures。

 to model different data to access that data it's a great way to think about traversals over compound data structures of different types and that'll be the focus in section2 we'll also do a little bit on tail recursion。

 which is the key thing you need to understand in order to use recursion efficiently in modern languages like we're using here。

😊，Then in section3， we get to what a lot of people think is kind of the biggest feature of functional programming。

 which is functions as first class values， having functions that you pass around to other functions return from functions put in data structures。

 it's a large topic， it has very interesting meaning。

 what it means to pass around functions and that'll be our focus in section 3。

 and then in the last section of part A will both learn type inference how you can have a language with type errors with a type system where the programmer doesn't have to write down types because the compiler infers them for us and a separate but important topic of modules support that ML has for collecting together types and values and functions over that type in a way that enforces that clients cannot misuse and abstraction。

 It's the way we think in this sort of language about separating an interface from an implementation。

So overall， these are several of the key pieces that give you a precisely specified introduction to functional programming built up piece by piece。

 and these are the top high level topics for Part A of the course。



![](img/3b79461de4a2e26a7c942013bce5d45b_3.png)

Now when we get into Part B， we'll first redo most of what we did in Part A in a dynamically typed language。

 what changes， what are the tradeoffs when you don't have very many programs being rejected before they run instead you just rely on runtime failures in a dynamically typed setting and we will get there when we get there and then in the second unit in part B。

 we will actually implement a programming language using an interpreter and that'll lead to a very nice discussion of how you implement programming languages。

 what it means to be a programming language and an implementation of it and show you that you can actually implement your own language well one that we give you。

 in fact， one that has first class functions， so often the best way to understand something is to implement it yourself and we are going to give you that experience with first class functions。

We will also in that section 6， if you will， the second unit in Part B。

 compare static versus dynamic typing， we don't do that right away in section 5 because first we want to get experience with dynamic typing。

 and then we can have a good discussion sort of comparing ML and racket along this important design dimension where they make different high levell decisions。



![](img/3b79461de4a2e26a7c942013bce5d45b_5.png)

And then in part C， we now visit objectoriented programming。

 which many of you would have seen before and it's okay if you haven't。

 and in the first unit we sort of do some basics in Ruby and learn a lot about Ruby and because it's our third language。

 we see that we can actually learn a lot quite quickly。

 we focus on how it' sort of even more dynamic than racket and how it is even more objectoriented than you may be used to in languages like Javas C sharp because in Ruby really everything is an object。

 even numbers are objects and then in the last section of the course。

 we compare objectoriented with functional and we do a number of more advanced objectoriented topics。

 things like mixins and double dispatch and that makes the last homework of the course fairly challenging when we use some non-trivial objectoriented idioms to compare some of these ideas。

So I really encourage Part C， of course， that's a long way off from us。 A lot of people think well。

 I already know OOP， I'm really here for the functional stuff， so I'm not going to do Part C。

 I encourage you to continue to part C exactly for that compare and contrast in complementing things I think it's also worth pointing out that some people who have done part C feel that I'm kind of antioO and I'm somewhat unfair to object oriented programming compared to functional programming。

 I think that's mostly not true， I have no problem with object oriented programming。

 but I am somewhat purposely in this course pushing the functional perspective because it's the less wellknown one and I think it's a good opportunity to do so。

 and to point out that while yes， there are situations where the OOP mindset is ideal let's investigate some where the OO mindset is possible but arguably not ideal。

 So yes， there are some things in the last homework assignment that I make you do in an object way even though。

😊，That tends to be somewhat cumbersome。 And this is not a criticism of any language。

 There are languages that encourage objects， but give other ways to do things。

 There are languages that encourage functional style， even when the functional style is not perfect。

 So you will， you will not see from this course from the beginning to the end。 me say， you know。

 one approach is always better than another approach。

 I do point out when the functional approach is a good one。 Sometimes even when it's a better one。

 But you will leave this course with a lot of food for thought and a lot of new perspectives。

 and that is my entire goal。 All right， that's the introduction。

 let's start and dig in with section 1， when you get to the next video。😊。



![](img/3b79461de4a2e26a7c942013bce5d45b_7.png)