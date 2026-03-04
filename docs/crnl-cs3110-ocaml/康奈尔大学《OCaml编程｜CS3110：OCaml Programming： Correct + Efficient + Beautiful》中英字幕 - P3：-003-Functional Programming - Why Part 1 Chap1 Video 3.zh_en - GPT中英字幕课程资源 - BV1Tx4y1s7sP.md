# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P3：-003-Functional Programming - Why Part 1 Chap1 Video 3.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Here are four reasons that I think are compelling for studying functional programming。😡，First。

 functional languages teach you that programming transcends programming in a language。In other words。

 if you'd have only coded in imperative languages before。

 you owe it to yourself to explore the other side of the world and see how it works。By the way。

 I would be making this argument if we started off teaching your functional programming in 1110。

 which some universities do more in Europe than in the US。If you were from that kind of background。

 I'd say， all right， it's time for you to learn an imperative language now。Both are important。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_1.png)

Let me draw an analogy here to studying a foreign language。

There are many benefits to studying foreign languages， besides just the language。

You get to learn about another culture。Maybe you find new things to appreciate and love and take back into your own life。

It can help you she your preconceptions， it can help reduce prejudices against other people by coming to understand them better。

You can even understand your own native language better by studying a foreign language。

This happened to me when I took Spanish in high school。

 I never understood how to use the subjectjunctive mood in English。 Do you remember what that is？

Well until I had to learn it in Spanish， that was。 And then I got a lot better at it in English。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_3.png)

Let me give you a quote from Alan Perlis。He's one of the most quotable computer scientists I've ever known。

Actually， I never knew him personally myself， he died in 1990。

 but he said a language that doesn't affect the way you think about programming。Is not worth knowing。

I promise you。Learning a functional language will affect the way you think about programming。

And hopefully you'll find that it's worth knowing。By the way。

 Pes was the first recipient of the Turing Award， which is considered to be the equivalent of the Nobel Prize in computer science。

And he won it for his influence in the area of advanced programming techniques and compiler construction。

So the very first Tin Award winner worked on programming languages， I think that's pretty cool。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_5.png)

A second reason to study functional programming。Functional languages predict the future。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_7.png)

What I mean by that is there are many features that existed in functional languages well before they were seen in imperative languages。

An example of that is garbage collection。So garbage collection is where the computer is automatically managing memory for you。

 say you're in Java and you're creating a bunch of objects。Well， at some point。

 the computer theoretically could run out of memory。Objects have a lifespan， though。

 right you use them for a while and then eventually you're done and you're never going to touch them again in your program。

The garbage collector is the piece of the language runtime that reclaims that memory that's never going to be used again。

And so it can recycle it and use it for other purposes。Java。

 which was introduced in roughly 1995 in its first version， had garbage collection。But guess what？

About 40， 50 years before that， the functional language Lisp already had it。

Lisp is sort of the grandmother of all functional languages。

 It's characterized by having lots of parentheses in its syntax。 and for that reason。

 there's a joke that Lisp actually stands for lots of irritating silly parentheses。

You can take a look at a listISP program someday and see whether you agree。

Lisp had garbage collections so early because it was the only reasonable way to implement the programming language itself because of all the memory management that was needed behind the scenes。

So it was a necessity to invent and design back then。

Another example of a functional language predicting the future is generics。

Java did not have generics to begin with。They were added in Java 5。By generics。

 I mean the language feature in Java where you can write a type parameter after a class。

 you can write list angle brackets T， for example， in that T is the generic。

 it's what you're parameterizing list on， so that's an example of parametric polymorphism if you remember that from 20110。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_9.png)

And there's other pieces of the Java language design that got complicated and ugly because generics were bolted on much later after the language had already been released。

The designers didn't want to break backwards compatibility with old code and tools。

 which made Java generics less useful in some ways than other languages like Microsoft's Charp。Well。

 in the functional language community， the power and expressivity of parametric polymorphism of generics was already well known。

 it had existed in a language called ML back in 1990。

So ML to be a little more accurate is not a language。

 it is a family of languages and we'll talk a little bit more about those in just a little while。

The language we're going to learn in this class is in that family。

And there are many other examples of this I could give， but I won't go into detail on all of them。

 brieflyefly， higher order functions were bolted on to C Sharp and Java later in their designs。

 Lisp had them back in 1958。Type inference was added to C++ in 2011。

 Java 7 in 2011 ML had it back in 1990。 and by the way， why did they add type inference to C++？

Because it was getting too hard for programmers to write down the very complicated types needed for what's called template programming in modern versions of C++。

And so when it gets too hard for a human to do it， you ask the computer to do it。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_11.png)

And what's next？I don't have a crystal ball， I can't tell you what the future is going to be。

But if I had to make a guess。

![](img/9651918fb8f0dd5d949f92e0259f6b3b_13.png)

I would say that one of the most compelling features that functional languages have to offer that haven't yet been adopted in many imperative languages at all is going to be pattern matching。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_15.png)

There is a language called rust that has added it recently。

Pattern matching is a feature you're going to come to know and love in this course。

 I think it's phenomenally powerful and useful。And by the way， don't get me wrong。

 I'm not saying that functional languages are the only place where new features are invented。

 absolutely not。Object oriented features， for example。

 are amazing and cool and have enabled us to build really big software have been useful for designing GuUI libraries that all computers now use。

I didn't come from the functional language community。In fact。

 functional languages have started to import object oriented languages as well。

 you're starting to see blends of these， a Scala is a good example。

So it's not that one language family is better than the other。

But functional languages do have a pretty good track record of predicting the future。

And that makes them useful to learn。Because the features you'll learn this semester。

 you may one day see show up in the next mainstream imperative language。



![](img/9651918fb8f0dd5d949f92e0259f6b3b_17.png)