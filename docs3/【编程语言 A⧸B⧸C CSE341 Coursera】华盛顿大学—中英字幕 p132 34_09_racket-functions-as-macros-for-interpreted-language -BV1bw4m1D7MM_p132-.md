# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p132 34_09_racket-functions-as-macros-for-interpreted-language -BV1bw4m1D7MM_p132-

In this segment， I want to cover the last topic we should need for our homework assignment where we're implementing a made up programming language inside of racket。

 and this is going to tie together our work on an interpreter with our earlier brief study of macros。



![](img/446795a8605f005b49248ecc34716543_1.png)

So here's what we know so far and I need to bring these two pieces together now for us in this segment。

 we are taking the following approach to implementing a programming language B in language A。

 what we're doing is we're skipping parsing and any notion of concrete syntax by writing language B programs directly in terms of language A constructors and then our interpreter is simply written in language A by recursively evaluating subexpressions in order to get results for larger expressions。

Now， here's what we know about macros。 We learned earlier that a macro extends the syntax of a language。

And what happens is you define a macro， and then when you use a macro。

You expand the macro use using the macro definition before the program is run。

 you rewrite the syntax of the program in terms of the macro definition。

 and this is all before the rest of the implementation of the language sees anything。

So what we're going to do now is see how our approach to language implementation is going to give us a way to write what are essentially macros just as rackcet functions。



![](img/446795a8605f005b49248ecc34716543_3.png)

So here's how this works， okay？We are just going to write racket functions that are going to take in language B syntax and produce language B syntax。

And if we use those when writing our language B programs。

 we will get the output of those rackcet functions put into our program。😡。

Before we call the interpreter。 So we're not going make any changes to the interpreter。

 we're not going to add anystruct definitions。 So is just a programming idiom where we can act like these rackcet functions are part of our programming language。

 They're not， they're racket functions that take in syntax and produce syntax。

 and then it's that result that then we end up thinking as as part of our program。

 which is then fed to the interpreter。 This all happens before we ever call a function like eval X。

 So it'll be much easier to see once I show you the code。 and everything I have here。

 I've shown you before。 and then we're going to define and use some quote unquote macros in this language。

 So in an earlier segment， I showed you this little language that has constants， negations。

 additions， multiplications， Booleanions true and false。

 a test for whether the result of two sub expressionpressions are the same number and in if then else。



![](img/446795a8605f005b49248ecc34716543_5.png)

And I showed you a function Eval X。 This is the correct version that handles error messages properly。

 And it's a big con that has one case for every kind of expression。

 There's no environment here because this little language doesn't have variables。

 but that's primarily a separate issue。 So we know if I just click run here that I could define a racket variable X that holds a program in this language like add of const3 and const 4。

And if I ask what x is， I see it's just a program， and if I evaluate it。I passed to my interpreter X。

 and what I get back is constant 7。Now let's define some racket helper functions for writing programs in this language and see how they kind of act like macros。

So suppose I wanted an and also an and in my language。 So this is a racket function。 All it is。

 I'm going to put a function body here。 It's a plain old racket function。

 It's just a racket function that I'm going to call with two expressions in my language。

And what I'm going to return is if then else， E1， E pool false。So I take in syntax， I return syntax。

 That's what macros do。 And now， once I have this defined。

 I could write a program like and also bull true。E nu cont 3， cont 4。Okay。

And what I get back is the expanded version。 I call this racket function with some syntax。

 I get back a program。 So if I。

![](img/446795a8605f005b49248ecc34716543_7.png)

Held this program in a racket variable， Y is the macro expanded version。

 So when I call eval x with y。I pass the interpreter， things the interpreter understands。

 I end up getting back false because indeed， I take this first branch that I have a conditional where it's true。

 So I get down here， but then three is not equal to 4。 So I end up with false。

So that is seeing how these racket functions act like macros。

 let's do a couple more because they're interesting and you need to do similar things on your assignment。

 here's another simple one， supposeupp I wanted to act like my function had double well then I could just macro expand in E into multiply E and the constant 2。

Let's do one that's a little different because it mixes kind of rackcet constructs and the language we're interpreting a little bit more。

 How about I have a macro that takes in a racket list。

And returns the program in my language that would multiply all the expressions in that list together。

 So maybe E's would be a better name for this function than X's， because it's a list of expressions。

 All right， So if the list is empty， then return the constant one。 I'm not evaluating anything。

 I'm not multiplying anything。 I'm creating a program that when run will be the multiplication of everything in this list。

 Otherwise， I have a non-empty list。 So let's create multiply out of the first thing in that list And the syntax I get by calling list product on the rest of the list。

😊，Let's see a little bigger example of a program we might write that would use all of these macros we've defined noticeice you can use them anywhere。

 you don't have to use them at the top of your program here I'm using and also on how about doubling for。

Okay， is that equal to the product of the racket list。

 Because that's how I define the list product macro， if you will。

 of how about cons 2 and cont2 and cont 1 and cons 2。

And this time I'll end that with just the constant true。And now if I run this。



![](img/446795a8605f005b49248ecc34716543_9.png)

Test is just syntax。 I haven't interpreted anything yet。

 and it's kind of big because it expanded everything out。

 It's an if then else because that's the expansion of and also Eum of look。

 the double of cont4 became this multiply of cont4 and 2。

 and the called a list product became a multiply of a con， a con。

 It's all nested multiplies all the way down。And the reason why I didn't just do the multiplication is because。

 first of all， that's not how macros work。 And second of all。

 if my language had things like variables or functions， I can't do the multiplication yet。

 I could have variables in some of these expressions。

 The whole point is to produce syntax that represents the expanded thing so that we can then evaluate it and get our result。

 So again， test is just that big piece of syntax and then I could evaluate test and I would get true。

So that is the role of macros， that is the sort of thing you will do on your homework assignment let me just finish up with one thing for those of you who did the optional material on macros where we looked at hygiene issues earlier I really brag that rackc's macro system is superior to the macro systems in most languages because of the way it handles variable shadowing and the way it's okay to use local variables even inside of macros in racket without things getting messed up。



![](img/446795a8605f005b49248ecc34716543_11.png)

Now I've defined a different way to do macros for this embedded interpreted language。

 and this approach is not one of those good ones， it does not handle variable shadowing the way you would expect。

 so if you want to define one of these macros via racket functions and you had a language that had variables in it。

You would have to do things like use strange variable names in your macro definitions and things to avoid having sort of surprising semantics in the presence of variable shadowing。

Nonetheless， the general idea holds that we can think of a rackcet function that produces syntax for our language as a macro for that language。



![](img/446795a8605f005b49248ecc34716543_13.png)