# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P158：-158-Calculator_ Evaluate Integers Chap9 Video 5.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

To interpret a string， I need to parse it。Evaluate it。And then convert it back to a string。

So I'm going to factor my in function here into those pieces。

So I have implemented two helper functions here to help with interpretation。

 one of them is string of Valal， which converts an expression E to a string。

 and as a precondition I'm going to require that E is a value。

 so I am going to have a notion of values that are done computing there's no further evaluation to be done with them just as we had in OCM。

Its Evals job to fully evaluate expressions down to values。Okay， let's implement string of vow first。

 that's the easy one。Since we only have one kind of AST node thus far， which is int。

 it's easy to convert that to a string， integers are already values。

 there's no computation to be done with them so we can just call the built in standard library function string of int on the data carried by that node。

😡，Evaluation， though。We're going to need a little bit more work for that。

Not because integers are themselves hard to reduce the values， in fact， they're already values。

But we're going to structure evaluation of ASTs using an idea called a step of computation。

 We want to take one single small step。And keep taking small steps until we've eventually reached a valley。

Okay， I've built out the bones of my implementation of the Eval now。

What does it do first it checks to see whether E is already a value。

 and I've written a helper function is value to do that。At this point。

 all of the nodes in my ASTs are values because I don't have complicated expressions yet like plus or times。

If he's already a value， then I'll just return you。Otherwise， I'm going to take E。

 do one single small step of computation with it。😡，And then recursively call Eval on the result。

So aal essentially is just going to keep calling itself and calling itself until it gets down to a value。

Now， what does step do？Well， for an integer。There's no computation to be done。In fact。

 you can think of it as the computation has already finished。😡。

So although this might seem a little counterintuitive at first。

 I'm going to say that when I reach an integert there's no step that can be taken。

 and I'm actually going to raise an exception here， does not step。

Now notice I should never get that exception right if the rest of my code is working correctly。

 then by the time I call eval on an integer， it's already going to be a value。

 is value going to return true， so I will never end up calling step on an int。😡，O。

Now we should be able to make our first test case pass。 Remember。

 our first test case is just checking whether 22 evaluates to 22。And it does that test case passes。

 yay， so I can parse 22。

![](img/785d71e02eefb7230a375b78b43ae7ae_1.png)

And now I can interpret it as well。