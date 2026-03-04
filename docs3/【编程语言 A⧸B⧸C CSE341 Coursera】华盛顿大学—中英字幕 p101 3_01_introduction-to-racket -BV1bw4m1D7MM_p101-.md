# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p101 3_01_introduction-to-racket -BV1bw4m1D7MM_p101-

This segment is the beginning of the first of a couple sections and we'll use the rackcet language。

 so we need to start by getting used to a new programming language and we'll do that here。

 so we're going to use the rackcet language instead of ML。

 we're going to recommend the doctor rackcet programming environment instead of another editor so we won't use emX for this part of the course and we have installation and usage instructions on the course website I think you will find installation here very simple and straightforward so just do it when you have a few minutes。



![](img/b31302b8271119f3a7ac9aa1cf0777f6_1.png)

Like ML racket is a mostly functional language so a lot of what we've learned in ML we just get to see in a new setting we'll still have anonymous functions。

 we'll have first class function closures everything's an expression so we don't need things like return statements and so on we're not going to use racket with a form of case expression it does have support for some of that but we're going to access our one of types in a different way and that will be fine for our purposes but there's two key differences from M that make me want to use racket for this portion of the course。

 The first is that it does not rely so much on a static type system It accepts many more programs and that just delays what in ML would be a type error until something occurs at runtime so if you want to try to add a number and a string it will be just fine until you actually get to that expression and then you will get a runtime error the other thing is you'll see in future segments when we start writing some real code is that racket as a very。

Minimalist syntax。 It uses parentheses a lot to group things rather than having strange syntax rules。

 like most other programming languages。 and it has many advanced features。

 We won't have time for most of them， but I want to at least have some optional discussion of the module system if we have time。

 I do want to discuss macros and so on。 Now overall， because of the similarities with M。

 The next homework assignment is not just going to be a get used to racket assignment。

 The first problem or two will be。 but after that， I want to talk about some new concepts。

 some new things that we could have done in M but work out a little more cleanly and racket。

 So we'll have some segments to get used to racket the language。

 but then we're going to move on because the course is not just about trying out the same thing in different languages。

 it's about learning new concepts。

![](img/b31302b8271119f3a7ac9aa1cf0777f6_3.png)

I should mention that there's a related programming language called scheme racket essentially evolved out of scheme and was evolving for a while in about 2010 the designers of Racet decided to stop using the scheme name so that they could be more different without feeling that about it if you will。

 I might occasionally slip up and say scheme because I'm still used to calling languages like this scheme。

 I'll try not to but just don't be confused if I do so in case you have programmed in scheme and it was a very popular language。

 particularly in introductory programming languages as well as for real use Racet has made some non-compatible changes the ones you're most likely to notice are related to how lists are used and in particular that like an ML list elements are not mutable okay so if you've seen scheme before you do need to get used to that。

 if not we'll just introduce racket as its own wonderful modern programming language。

I should mention that as a modern language it's been used to build some real systems and continues to do so to be used in that way。

 it's also used a lot in education which is probably what it's best known for the language does continue to evolve so it can be a bit of a moving target I'm trying to keep everything up to date it doesn't move that quickly and you can always consult the online documentation in particular the rackcet guide is a free user' guide that covers the important concepts of the language and has much more than what we need in this course but it's easy to look up things as you need them。



![](img/b31302b8271119f3a7ac9aa1cf0777f6_5.png)

So to get started， I'm going to show you Dr。 Raet here in just a second it's going to have what it calls a definitions window and an interactions window this will feel very familiar to us in EmX we had the buffer where we wrote the code and the Reple where we ran the code。

 Dr。 Raet is going to work the same way I think you'll find it more user friendlyriendly than how we used ML and you know it will be fairly easy to learn on your own ask questions if you have them on the discussion forum and the lecture demos of course will show me using the tool。

And as I mentioned there's wonderful documentation。

 the general Racet website is where you download Dr。 Raet， and there's the racket guide。

 there's many tutorials， there's no shortage of information。



![](img/b31302b8271119f3a7ac9aa1cf0777f6_7.png)

So why don't I flip over here now so here is Dr。 rackcet and this is just the current buffer I'm showing you is just a buffer where you can write code and then when I want to run it I can just clicked this run button here in the upper right and now I get this split where I have a repple below and the code up above you can flip between these the menu options have options to show just one or the other I think control E cycles between showing just the definitions and the definitions and the Reel so I'm just hitting control E to switch back and forth here。

 and this is pretty much what Dr。 racket will look like for you except I've increased the font size and change the font so that it looks a little better in the recordings。

So now let's look at the actual code。 This brownish text。 you see are comments， comments in racket。

 start with a semicolon and go until the end of the line。 There is support for multiline comments。

 I won't tend to use them much。 This is fairly conventional to just have each line of a comments start with semicolon。

 and you can have comments on the same line as other code。 You just have to have it to the right。

 So this here down the bottom。 This is another comment。



![](img/b31302b8271119f3a7ac9aa1cf0777f6_9.png)

A couple bookkeeping things we're always going to do in our files。

 The first is to always have the first noncomment line in your file be exactly this。

 I'll type it again for you， although you should only have it once hashl racket okay that tells Dr。

 Raet that this is racket code in this file Dr。 Raett actually supports defining your own languages running code in lots of different languages so we have to say which language our code is and we say it with this first line。

This second line provided all to find out is a bit of a work around to keep things simple for us by default in racket。

 it has a module system just like we studied in ML， but in rack's module system。

 each file is a module and by default， everything in it is private and you have to say what you want to make available to other files。

Using our methodology in this course of putting our tests in a second file， that's a bit cumbersome。

 So this one line， which you can just copy or we'll give it to you for the homework assignments。

 says change the default。 make everything public。 And that makes your code much easier to test。

 So with those two things out of the way。 you then in the rest of your file。

 just defined a bunch of definitions， variables， other things。 And for this lecture。

 I've just done one， we'll do a bunch more in the bunch more in the next segment。

 And I've defined the variable S to be the string constant hello。 So when you define a variable。

 it's open parenthesis keyword， defined name of your variable， string hello。😊，Close parenthesis。

 So this is like a v binding N Ml。 This would be like v S equals hello。And if I go to run this。

When I click this on the Reple， it did run all the code so it did create that definition for S。

 unlike an ML， it doesn't tell us any information。 it just you know it would give us an error if something didn't work。

 but since everything did work it just gives us our prompt and I could say here I could add two and2 and I would get back four that's how you do addition in racket parenthesis plus the arguments and another parenthesis I do have S right I get the string hello right there。

 if I use a different variable like T。 I get an error message that I have a reference to an unbound identifier So that's just seeing Dr。

 Raet will continue to use it in the next few segments as we introduce the racket language quickly covering a lot of the same ideas we already saw in M and then after a few segments of that。

 we'll move on to new concepts and new material。

![](img/b31302b8271119f3a7ac9aa1cf0777f6_11.png)

![](img/b31302b8271119f3a7ac9aa1cf0777f6_12.png)