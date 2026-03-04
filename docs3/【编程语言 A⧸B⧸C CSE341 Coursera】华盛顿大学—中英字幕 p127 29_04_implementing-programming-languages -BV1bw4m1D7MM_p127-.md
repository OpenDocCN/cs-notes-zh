# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p127 29_04_implementing-programming-languages -BV1bw4m1D7MM_p127-

On our next homework assignment， we're going to implement a small programming language。

 and so I want to in this segment start explaining in general how one goes about implementing a programming language and then more specifically zoom in on the particular simplified setup and useful setup we'll use on our homework assignment。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_1.png)

![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_2.png)

So here's a typical workflow for an implementation of a programming language Think of it as first taking it in some string which is the text of the program someone writes down。

 it would be in a file， of course， but we could read that file in and we can think of the contents as being in a string and we'll call that string the concrete syntax。

 it's the syntax the programmer actually wrote down。

The first typical stage is to pass that syntax to the parsing procedure， the parser。

 and as we've all seen if we've programmed， we often get error messages。

 It's the job of the parser to give us syntax error messages。

 things like a parenthesis in the wrong place or using a keyword in the wrong position or something like that。

 But if we don't have any syntax errors， the output of the parser is what is called an abstract syntax tree or AST。

 So it's still syntax， but it's in a much more structured form than what the programmer wrote down。

 It is a tree that shows what constructs in the language are being used and how So in this example we would say that we have a function call。

 function calls would have， say two children in this case， the first expression in the second。

 The second one here says， oh it's a constant and the particular constant is for the function has an argument X and then its body。

 its body is an addition expression。 the two subexpressions of the addition are both variables with X and we build this entire tree。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_4.png)

3That gives us the structure of the program that we're supposed to implement。

At that point your language might have some sort of type checker that runs over this tree giving additional error messages。

 like if instead of having a number that we pass this function， we tried to pass it another function。

 it would say， well that's parses， I can create an abstract syntax tree from that。

 but I get a type error message and if I don't have any of those。

 then I pass this AST onto the rest of the implementation which is in charge of running the program and giving an answer。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_6.png)

So now let's talk about the rest of that implementation。

 I would say that there are basically two fundamental approaches to implementing some programming language that I'll call B on this slide if I want to implement B。

 one approach is I could write an interpreter in another language A right my interpreter has to itself be a computer program so I'll use the language A to write an interpreter for B now interpreter is not a great name。

 a better name would probably be something like avaluator or executor or something。

 but okay everyone calls it an interpreter so we will as well and the idea is to just take that syntax tree and B and come up with what the answer would be if you ran it。

 maybe on some input that's provided when you run the program。

The second approach is to use a compiler。😡，So the idea with a compiler is it is itself， of course。

 written in another language A， and it produces a program in a third language C。

 and then we just take that program and we run it。So compiler is also a terrible name。

 a better name would be translator， but it's been called a compiler for many decades and so we will call it that too。

 and the key thing you have to do is take a program in B and produce a program in C that's equivalent that has the same behavior and then you have to rely on there already being an implementation for C。

 so if C is binary code， the kind of code that your computer hardware can run directly。

 then you can think of the computer hardware as an implementation of C and so your implementation of B just translates to a program in C and then you run it on the hardware。

So this language A that we use to implement our language B will sometimes call the meta language。

 and a key thing we have to do in this section of the course and on your homework is in our heads。

 keep straight what's A and what's B， what is something in the language we're using to implement a language and what is in the language that's being implemented。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_8.png)

I should mention that by the way the reality on Li learning languages is certainly more complicated。

 it's not just you have an interpreter or you have a compiler。

 Moern language implementations tend to do combinations of these two fundamental ideas for example most implementations of Java start with a compiler that translates your program but not all the way down to binary just to some intermediate language it's often called bytecode then there's an interpreter for that bytecode language。

 but that can be a little slow and so that interpreter includes a compiler for compiling down to hardware。

 and then most people would think well once once you're in binary I mean then it's just interpreted by the chip but in fact modern chips at least for the X86 say well actually we don't want to interpret quite those instructions so when the program's running will actually translate things internally in the chip into even smaller instructions and then interpret those so the point is there's two fundamental ideas that can be combined in interesting ways。

R， the implementation of racket has a similar mix。 This is nothing specific to Java， but。

The ideas are you have an interpreter or you have a compiler。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_10.png)

One other thing I have to mention is that a language is defined by written rules for what are the semantics of the different constructs in your language。

 whether it is implemented with a compiler or an interpreter or some combination thereof is an implementation detail。

And so once you understand that， it should be obvious that there is no such thing as a compiled language or an interpreted language。

 there are implementations of a language that use an interpreter or implementations that use a compiler。

Unfortunately for decades people have confused this notion and you will often hear such phrases like C is faster than Lisp because C is a compiled language and LispP is an interpreted language and I wish to emphasize that this really does not make very much sense and I for one。

 like to politely correct people when they repeat these old sayings that are just by definition not just wrong but don't really make sense Now I will add there is a way that they make sense at the end of the section I'll talk a little bit about how languages like Ra racket have an eval construct when you have an Eval construct in your language you need to have a language implementation that's still around at runtime when the program is running because you may need to implement other programs in the language but there's no reason why EVal can't be implemented with a compiler just as well as an interpreter。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_12.png)

Okay so that's the end of that sermon let me now go back to this workflow and tell you that on your homework assignment。

 we're not going to do the parser and we're not going to do the type checker we're just going to do an interpreter and I want to emphasize to you how you don't really need a parser if you set things up correctly in how you implement one language inside of another one so let me show you how we can actually skip the parsing step。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_14.png)

![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_15.png)

Suppose we wanted to implement programming language B in programming language A。😡。

What we could do if we didn't want to write a parser is have programmers writing programs in B。

 write the ASTs， the trees directly in programming language A。

 so they don't write strings that we then convert to the abstract syntax trees。

 They just write the abstract syntax trees。😡，And if our programming language A is rackcet and we give B language programmers strs。

 this is really not so bad， what they're doing is they're writing down rackcet data structures that are exactly the AST that represents a program in the language we're trying to implement。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_17.png)

So for example， maybe you would have some struck definitions like call and function in Var。

 and if a programmer came along and just used these racket constructors in this way。

What they're essentially writing down is this picture on the left。

They are writing down exactly this tree。 you can actually read it， you just have to turn it sideways。

 you have call with two subexpressions， two subtrees。

 a function that has an argument list and in addition， on the other side。

 sorry we shouldn't have a negation here， it should just be a cont。

 but if they did want togate and come up with negative four， they could have that and so on。So。

This is how we can get programmers to not give us strings， but to give us trees directly。

 we just have them write down their programs inside of racket using constructors。



![](img/e9c5fb2c7841eac1d3ab71d20ea6ccbd_19.png)

是啊。This is already what we were doing with our arithmetic expression example in the previous segments。

😡，Think of the expressions build out of constant gate。

 add and multiply as forming a little programming language。 Let's call it the arithmetic language。

 All right， so we are using racket as our meta language。 That's our language， a。

Our language B that we want to implement we'll call the arithmetic language。😡。

People writing programs in the arithmetic language just use the racket constructors to write down the abstract syntax tree。

AndThen our language implementation is the EvalLX program。 this is an interpreter。

 this is exactly what interpreters do， they take a program which is written down in racket using these trees。

 and they produce an answer in the language， and so we have already implemented a programming language we have in this language。

 constants， negations， additions and multiplies。😡，The program itself is a rackgged data structure。😡。

But it is a program in a language and the implementation of that language is the Eval X function。

 so now all we have to do to get ready for our homework is learn how to implement more interesting language constructs than just negations。

 additions and multiplies， but we have the framework that we need。

