# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p99 1_03_overview-of-part-b-concepts -BV1bw4m1D7MM_p99-

All right， what I'd like to do now is give a very brief overview of what we're going to focus on in Part B and how it fits together and builds on what we learned in part A This is always difficult to do both because there's no brief way to talk about so much substantive material and also because we haven't seen this material yet so I don't want to discourage you in any way if I use any jargon or terms that don't make sense to you yet。

 they're not necessarily supposed to， but I hope this overview gets you excited for the material that's coming ahead shortly。



![](img/70cba454c5913bd19036e0443adde0ce_1.png)

![](img/70cba454c5913bd19036e0443adde0ce_2.png)

So in part A， you can really think of it as learning the basics of functional programming and how to think about language constructs。

 starting with things like functions and recursion and environments and simple data structures like tus and lists and then we got into pattern matching and data types and then we studied firstclass functions and closures and then in the last section of part A we studied type inference we studied the module system and we discussed when two expressions could be equivalent and what equivalentence means in a programming language and when you put it all together。

 you end up with a precisely specified introduction to programming that gives you enough power to do a lot of things and compose things elegantly。

 and we did it all in a statically typed functional programming language namely MLl that we built up piece bypiece and now what we're going to do is transfer those ideas to racket and build on them and here's what we're going to do first。

 in section 5， which is really the first section of this。



![](img/70cba454c5913bd19036e0443adde0ce_4.png)

Because we're just continuing from part A， if you will。

We're going to quickly redo in a dynamically typed language a lot of what we did in ML what I mean by dynamically typed is there won't be a type system。

 there won't be type inference， will' basically be allowed to try to do a number of things that ML would reject before running our program。

We'll have different syndaxs， as you'll see shortly， rackcet uses lots of parentheses。

 but we'll see a lot of similar things that focus on lists and closures and functions and many other things。

After that， in the same section， because redoing what we already know doesn't take very much time。

 We're going to focus on delaying evaluation。 We're going to see a number of powerful programming idioms that involve using functions that take zero arguments。

 Now， you might think what's the point of taking zero arguments。

 Why have a function if you're not passing in any information。

 And the answer is that function bodies are not evaluated until you call them。

 which turns out to be exactly the idea we need for a number of advanced idioms。

 things like creating data structures that behave like they're infinitely large things called streams that will be a big focus on the homework in this section。

😊，And then lastly I'll touch on macros， I'm going to make a lot of the material on macros optional because it's not a major focus of the homework。

 but it's a good fit for this part of the course for a couple reasons， first of all。

 rackcet has a very welldesigned macro system， so it's a good environment for studying macros and also in the next section we're going to need the basic idea for some of what we're going to do macros if you haven't heard of them are essentially a way for programmers to extend the syntax of a programme language。

 so being able to grow a language by introducing new things into the language without having to change the underlying language implementation。

Speaking of language implementation， that's a big focus in the second module of Part B to get there we'll first have to study how racket does things that M would use data types for so rackcet。

 it turns out in a dynamically typed language， things like M's data type bindings don't make a lot of sense。

 but similar things do and so we'll study that and then we'll use that to implement our own programming language so we'll talk in general about how programming languages are implemented。

 we'll talk about how you represent a program not in terms of strings of characters but in terms of something more structured typically with trees and then we'll learn how to implement not only basic things like addition and pairs and variables。

 but function closures In fact in this part of the course the homework will be implementing your own interpreter for a small programming language but a programming language powerful enough to have firstclass functions。

 something。Programmers could use to implement their own things like map and filter。



![](img/70cba454c5913bd19036e0443adde0ce_6.png)

And then kind of not really directly addressed on the homework。

 but an important part of the course is saying now that we've used M and we used racket。

 let's focus on the biggest difference between them。

 which is whether you have a static type system or not and we'll take a big step back will define what static checking means will learn important terms like what it means for a type system to be sound or complete and why you cannot have both typically and then we'll discuss advantages and diss of static and dynamic typing and as well probably not surprise you。

 I won't take a firm opinion on which is better instead I'll focus on tradeoffs between them and sort of things that are indisputable things that are clear facts and then it will be up to you to kind of weight those facts to decide for your own projects for your own programming for your own preferences。

 which approach you prefer M's more strict static approach or rack's more lenient dynamic approach and that in a nutshell。

Is part B of programming languages in terms of the content that we're going to cover？



![](img/70cba454c5913bd19036e0443adde0ce_8.png)