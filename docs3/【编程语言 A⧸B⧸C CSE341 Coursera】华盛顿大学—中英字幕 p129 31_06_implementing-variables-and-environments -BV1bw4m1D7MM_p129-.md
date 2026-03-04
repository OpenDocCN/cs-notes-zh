# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p129 31_06_implementing-variables-and-environments -BV1bw4m1D7MM_p129-

In this segment， I want to talk to you about how to implement an interpreter for a language that has variables。

 This is important for a couple reasons。 First， real programming languages have variables。

 And second， the language your interpreting on your homework assignment has variables So notice that so far the interpreters we've written didn't have anything like variables let expressions。

 functions that took arguments and so on。 once we have those things。

 we need to change how our eval with X function works to take into account that it may need to look up variables as it's evaluating a program。

 So the idea here is I'm not going to show you the code in this segment because that's your homework problem。

 but I am going to describe in English exactly how the interpreter should work。

 So it's really your job to code this up on the homework assignment。 Fortunatelyly。

 the way variables and environments work is really exactly as I've been teaching since the very。

 very beginning of the course when we first learned the very beginning of Ml。

 and what better way to really。

![](img/3cef603a30940fc858ed1e3532dbc80d_1.png)

![](img/3cef603a30940fc858ed1e3532dbc80d_2.png)

![](img/3cef603a30940fc858ed1e3532dbc80d_3.png)

![](img/3cef603a30940fc858ed1e3532dbc80d_4.png)

Make sure we understand the semantics then to have to implement that semantics for a small programming language。

 like you will on the homework。

![](img/3cef603a30940fc858ed1e3532dbc80d_6.png)

So here's how we do it。When we're interpreting something， when we're evaluating an expression。

 we do that with a current environment。An environment is what I've always said in environment is。

 it maps variables to values。Now on our homework， how are we going to map variables to values。

 Let's just have a list of pairs where the first thing in every pair is a string。

 This is a racket string that says what variable we're talking about。 And then the value。

 that's one of those values in the language we're interpreting。

 It's one of the expressions that could be returned by the evaluation and an expression。

 So something like a constant or a closure or a boolean or whatever it might be。

 And if we had a list of these pairs that could work as an environment。

And we would pass into our interpreter the current environment。Okay， so you get it as an argument。

And then when you have a variable expression， you do what I've always said you do to evaluate variable expressions。

 you look them up in the environment。 There's nothing magic about that。

 We get in the environment as an argument to the interpreter， When we have a variable， we look it up。

😊，Now the interesting part。When we recursively evaluate sub expressionpressions。

 we will need to pass an environment to the interpreter for those subexpressions。Now。

 for a lot of expressions， it will be the same environment that we were given。

If you have an addition。Then you need to recursively evaluate the two sub expressionpressions using the same environment。

So if it was adding the variable X and the variable Y。

 we'll pass in the same environment to the first subexpression， which willll look up x。

 and we'll pass the same environment into the second expression that we'll look up Y if x or y is not in the environment。

 as you might imagine， the interpreter case for variables， will as part of its lookup procedure。

 give an error message saying that it did not find the variable。Now。

 sometimes when you evaluate a sub expressionpression， you do it with a different environment。

 perhaps the most obvious example is if you have a let expression。

 when you evaluate the body of that lead expression， you need a larger environment。

 you need a new pair in it so that the body of the lead expression。

 the body can use the variable that was defined by the lead expression。

So that's really all there is to it in terms of variables and lead expressions。

 Let me describe a little bit more the setup here。

![](img/3cef603a30940fc858ed1e3532dbc80d_8.png)

ok啊。In your interpreter now， you should really think of there being a recursive helper function。

 we might call it eval under end for evaluate under an environment and it takes in two arguments。

 in expression E yes， but also an environment well call it EV。

 and this is where your big cond is with one case for each kind of expression。

 the variable case will need to use the environment。

 some cases when making recursive calls will just pass the same environment。

 other ones will pass a slightly different environment。



![](img/3cef603a30940fc858ed1e3532dbc80d_10.png)

So this is where all the action is， but then your run a program。

 your Eval X for the entire program would then just call EVval under N and the only question is what environment do you start with and the answer is the empty environment just the thing that has no pairs of strings and values in it because we start without any variables being in our environment。



![](img/3cef603a30940fc858ed1e3532dbc80d_12.png)

Okay so the only thing I haven't told you is the actual representation of the environment。

 the representation of the environment is just a racket list on your homework。

 it can be anything you want a racket list containing racket pairs where each pair is the string that is the variable we are mapping to something and then the Mple value on the homework we call the language being interpreted Mple stands for made up programming language and that would be something like the constant 17。

 which on your homework is written into 17。That's the entire setup。

 I want to finish with one grading detail。 One stylistic issue is if you look at it Eval under end is really just a helper function for eval X Eval X calls eval under end with the empty environment。

 you should not generally call eval under end directly that wouldn't make a lot of sense。

 It's just a recursive helper function for our interpreter So you might be tempted to therefore make eval under end a locally defined helper function of eval X and please do not do that and the reason is for grading scripts in order to be able to test your interpreter and figure out which parts you got right and which parts you struggled with。

 we want to be able to call eval under end directly with particular environments this way if you mess up a little bit of how you handle environments。

 you won't miss all the tests so we need you to leave Eval under end up at the top level of the file。

 even though in general， you could certainly make an argument。😊。



![](img/3cef603a30940fc858ed1e3532dbc80d_14.png)

It would be better style to just make it a locally defined helper function。

 And that is really everything you need to know to implement variables and environments for a programming language。



![](img/3cef603a30940fc858ed1e3532dbc80d_16.png)