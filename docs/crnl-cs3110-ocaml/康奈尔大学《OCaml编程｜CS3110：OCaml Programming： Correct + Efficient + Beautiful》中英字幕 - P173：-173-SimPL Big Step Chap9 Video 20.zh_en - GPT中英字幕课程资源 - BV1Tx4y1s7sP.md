# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P173：-173-SimPL Big Step Chap9 Video 20.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we've completed a small step interpreter for simple。

 let's write a big step interpreter for it to appreciate the difference between those two styles of semantics。

 those two evaluation relations。The big step semantics for simpleim is as follows。

A value big steps to itself。A binary operator， E1 plus E2， big steps to V。If three other things hold。

First， E1 must big step to V1 of value。E2 must big step to V2。

And V must be the result of doing the primitive operation V1 plus V2。

A variable name by itself does not big step that goes back to what we talked about before。

 it indicates an unbound variable。😡，A let expression， let x equal e1 in e2。

 big steps to a value v2 if two other things hold。First， E1 must big step to a value V1。

And then E2 with V1 substituted for x must big step to V2。

The if expression semantics are quite parallel to one another。

And if expression steps to the value corresponding to the appropriate branch based on what the guard big steps to。

 so if E1 big steps to true， and if E2 big steps to V2。

 then the entire if expression big steps to V2 and symmetrically for the false case。😡。



![](img/85a6da5bceda5f860715cab92ae4a5e3_1.png)

Let's implement the big step interpreter for simple。😡，The AST， the Lexer， the parser。

 those all remain exactly the same as in the small step case。



![](img/85a6da5bceda5f860715cab92ae4a5e3_3.png)

The only thing that changes is a little bit of the implementation here in Maine。ml。😡。

None of these error messages change。 Substitution doesn't change。 It's implemented the same way。

 What changes is we get rid of the step function， and now our eval function is going to be responsible for doing all the work。

So Evalal is going to take an expression and return a new expression that returned expression is going to be the value to which the input expression big steps。

 so let's get started implementing eval with big steps。😡，Okay， let's pause here。

I've implemented most of the Eval function， although it still has some helpers left that I need to implement。

An integer or a Boolean， since they are already values， big step to themselves。

 so eval of those just returns B。Trying to evaluate a variable， of course。

 returns an unbound variable error。Evaluating a binary operator or an if I'm going to push those off to a helper function。

 we'll get to those in just a minute。😡，To evaluate a let expression， first。

 I need to evaluate E1 to evaluate V1。😡，Next， I need to evaluate E2， but I need to substitute。😡。

V1 for X inside of it。So let's do the substitution。And now I need to finish by evaluating E2 prime。😡。

Now that I have a multiline implementation of it， it occurs to me it might be better to factor that out as a helper function。

 so that's what I'll do next。😡，That's a bit more pleasant of an implementation。And in fact。

 when it comes to implementing interpreters in this style， this is a common idiom。😡。

If we can't really do the evaluation in just one line with a short expression as we could up here with integers and Booleions。

 for example， then it's better to factor out a helper function for the evaluation of that particular syntactic form from the language Now let's finish by evaluating binary operators and if expressions。

😡，I'll pause right here。What I've done is to evaluate E1 and evaluate E2。

 I'm going to pattern match against the result of that and the binary operator all at the same time。

To evaluate a binary operator， I check and see whether it's an ad multiplication or less than or equal to。

 and the arguments then must have the right types。 they all have to be integers for this simple programming language。

 and I can return the corresponding value。 Anything else raises a be off error to indicate a type error。

Finally， we'll evaluate if expressions。We evaluate the guard， if it's true， we evaluate E2。

 otherwise if it's false， we evaluate E3。 any other guard， say an integer， results in an error。

And that finishes our big step interpreter for simple， we can run its test suite。

 which is really just the same test suite as we used before for the small step interpreter。

And make sure that all those tests pass。And they do， yay。



![](img/85a6da5bceda5f860715cab92ae4a5e3_5.png)