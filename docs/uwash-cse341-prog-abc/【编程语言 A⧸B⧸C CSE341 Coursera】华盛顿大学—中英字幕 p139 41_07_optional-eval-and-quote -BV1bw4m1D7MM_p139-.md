# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p139 41_07_optional-eval-and-quote -BV1bw4m1D7MM_p139-

In this optional segment， I want to introduce the idea of Evalal。

 this is something that rackcet and many programming languages have。

 It's an interesting language construct that's related to some of our discussion of implementing one language inside another。



![](img/0c495979ab950df9b07da5b79284b80e_1.png)

So languages that have Eval， which is what it's usually called work as follows。

 there's a way in the language to build some data at runtime， however you want to build that data。

 and the data we're talking about in racket is just going to be a list with inside of it。

 some numbers， symbols and nested lists that themselves have numbers and symbols and other list inside of them。

But then what we're going to do is think of that data as a program Now if you think about it。

 this is exactly what we're doing and learning how to write programs for interpreters written in terms of abstract syntax when we did it for our own little languages we use constructors but here we're just going to use lists and symbols and the data that we're going to treat as a program is not a program for some other language it's a program for racket we're going to while a racket program is running。

 build up some syntax for a different rackcet program and then what EVval does is take that syndax and run it so you can build and run one racket program as part of another one。

So since we don't know ahead of time when our rackcCet program starts running。

 what data it's going to build up and pass to EV， that means that while our rackCet programming is running。

 we better have still around an entire implementation of racket。

Now that's easy to do if you implement racket with an interpreter when you get to Eval。

 you can just have the primitive eval use the interpreter。 It's harder to do if you have a compiler。

 you would need to ship with each program that might use Eval the enough to do compilation and then run it itself。

 but that is not impossible。 So this is why people a lot of times think that languages with Eval have to be implemented with an interpreter and call them interpreted languages and they have a point in one sense。

 but technically that is not correct。So that's why sometimes people do call racket and interpreted language。

 it's because it has Eval， but of course that's a feature that you do not have to use and does not have to be implemented in terms of an interpreter。



![](img/0c495979ab950df9b07da5b79284b80e_3.png)

So now let me show you how you actually use it。 I'm just giving the sense here。

 you'll have to consult the documentation if you're curious and more of the details。

 and I'm not really going to justify any idioms that need Evalal。

 This is actually a fairly contentious subject。 I think most people would agree that Evalal tends to get overused that most of the times that programmers use it。

 It's not appropriate， but there are some uses that are very compelling and it's a very powerful feature。

 For example， the Reple itself in Dr racket is implemented in racket and I have to assume that somewhere in the implementation of that Reple。

 it's using Evalal。 It's even what the E and Reple stands for， read evaluate print and loop。



![](img/0c495979ab950df9b07da5b79284b80e_5.png)

So we're not going to use it for anything useful in this course。

 but there's no point in making it mysterious， so let's flip over to the code and I'll show you the same example you see on this slide and we can see how it's used。

So here's a function。 Make some code one。 I'm going to show you a second version in a second。

 and it's just a plain old racket function and it returns a list。 If y is true， it returns this list。

 otherwise it returns this list。 And let's look at what these lists are。

 So if I call make some code one with true。Make some code。1 with true， I get this list。

 And if I call it false。 I get this list。 These are just lists。 This first list has the symbol begin。

 Then a nested list holding the symbol print and the string high。

 And then the this list that has three parts in it， the symbol plus 4 in2。

 And the repple when printing these things just doesn't put the little quote， like if I say quote。

 begin， I get the symbol quote begin， because I already have this quote on the outside here。

 We know that anything in here is a list and， and the repple doesn't print those quotes。

 But it's just the list。 and， and to prove it to you， How about I here， I。

Use a little local variable because that'll make life easier here for me and say。

 define fo to be that list， right， So F is just list。

 And now I could ask what's the car of the cutter of fo。I would get the list print high。

 and if I said， well， what's the car of that？I would get print and so on。 So it's just data。

 but it's data that looks just like a racket program。

 And it's actually in the form that Eval is happy to take。 So if I， sorry， just said。😊，E well food。

It actually ran that as code， printed the string high and then evaluated to 6。

 I could have also said， how about Eval， the car of the cutter of Fo。

And then it just ran the program print high。 And so it just printed high。

 If I said eval the car offu， I'm going to get an error。

Because what I tried to pass to Eval was just begin and that's not a legal program。

 So that's how Eval works。 Let me just finish up with one other feature。

 which is that it's annoying to have to write code like list quote begin list quote print hot。

 no one would want to do that。

![](img/0c495979ab950df9b07da5b79284b80e_7.png)

So instead， there's a special form and racket quote。

That basically takes everything underneath it and treats it as nested lists and symbols， not numbers。

 So instead of writing this code on the left， you can write it on the right。

 And quote changes the definition that everything comes after it。 This plus 42 is not in addition。

 It's a three element list of the symbol plus and then a4 and then a2。

 that's very convenient for writing down code that you could then later pass to eval。 quote an eval。

 in fact， are just inverses in the mathematical sense， which is neat。

 The one thing you can't do with quote， is do any computation underneath。

 Suppose you did want to do some computation to decide what code to put here。

 that doesn't work with quote， It would all be part of the program you're creating。

 But there's this other thing called quasi quote that has a way in the body to mark an unquote that says。

 well， this part I actually want you to run now and then put the result into the syntax of the program I'm building。

You can learn about that on your own if you're interested。

 but now I just want to finish up by comparing this approach to EVval to what most scripting languages do。

 which is in languages like Python and Pl and whatnot， you can pass to Eval a string。

And what you're passing is a string whose contents ought to be a program。

So what we're doing in those languages is passing concrete syntax and Evalal is going to have to parse it and then is going to run it Now that might be more convenient。

 you can just type whatever program you want in a string。

 but it's much more painful for combining things。 This is the last time I'm going to emphasize that rack's approach of having the concrete syntax and the abstractac syntax be so similar。

 all those parentheses is actually very convenient it makes it easy for EVval to take a list instead of a string。

But nonetheless， in those languages， you can have a string。

 you can concatenate different strings together to build up a program， and then you can call Eval。

 They also often have an idea that is really quasi quoting。

 which is to inside of a string be able to evaluate some expression and have that result then be part of the string。

 This goes by different names and scripting languages。

 What Lisp and scheme and racket have been calling it for decades is quasi quote and unquote it's always nice to see the same idea coming up in different languages in somewhat different settings。

 And that is a very， very brief introduction to the idea of eval。😊。



![](img/0c495979ab950df9b07da5b79284b80e_9.png)