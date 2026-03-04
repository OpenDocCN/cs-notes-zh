# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P9：-009-Let Definitions Chap2 Video 4.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've been working so far with expressions as the fundamental building blocks of OKMl programs。

 now let's look at a second kind of building block， which is a definition。



![](img/a64e124fc0ddcf54101d1d0a1a4c26d1_1.png)

A definition lets us give a name to a value。This is essentially the notion of a variable from other programming languages except that the variable's value can't change。

So for example， we could say let x equal 42。We get a response back from Utah and now x means 42。

So let's take a close look at that response again。Again， let's start by reading it right to left。

Let x equals 42。 What did that result in， It resulted in a value 42 whose type was int。

And it is bound to the name X。That's what the v X there means。So now if I read it left or right。

I've got a value named X， which has type int and is equal to 42。

And when I evaluate X itself at the next prompt。What do I get back？I've got 42。And it's just an int。

 42 itself is the value of that variable x。X is the name， 42 is the value。

I could have other values so I could say let why type in if I wanted。

 I could put the type annotation in in fact。I am allowed but not required to put the parentheses in this type annotation。

 let Y of type end equal 3110。Al， so now I've got a value Y of type in， which is 3110。

 But the compiler could have figured out that type for me， I didn't need to annotate it。 And。

 in fact， in this limited instance， in a let。Definition， I don't even have to put the parentheses in。

 the syntax here is sufficiently limited that the compiler can figure out what I'm saying without those parentheses。

So y is 311？And now that I have two of them， I can say things like x plus Y。

Which is now 3152 I think that's especially interesting because you take these two really great integers already。

 3110 and 42， you add them together and you get the number of the game design course that's pretty cool。

😊。

![](img/a64e124fc0ddcf54101d1d0a1a4c26d1_3.png)

Now that we've taken an intuitive look at let definitions。

 let's set back and examine them a little more carefully。

So definitions are a way of giving a name to a value。But definitions are not expressions。

 nor are expressions definitions。 You can see that in the Venn diagram here in which they are completely distinct classes of syntax in Ocal。

All right， so you can't take a definition and treat it as an expression or vice versa。Nonetheless。

 definitions do syntactically contain expressions in our previous examples。

 we were writing down integer values as part of definitions， those are themselves expressions。

So the syntax of a let definition is just let x equal E where x here is standing for an identifier。

So OamMel has rules for forming identifiers， you might think of these as variable names and they're very similar to the rules for identifiers from other languages。

 you can look them up in the manual， they do have to start with lowercase letters for these let definitions later on we'll see some examples of identifiers that start with uppercase letters as well。

 but OCmel is actually particular about that。You will get error messages if you try to start one of these identifiers with an uppercase letter。

The E here is any other expression that you might want it to be。

 according to any of the other expression rules we've seen so far or that we will see later。

To evaluate a let definition， this is the dynamic semantics recall。First。

 evaluate the expression E to evaluate V。Then bind V to X。

 So bind here means associate with associate the value V with the name X。 Henceforth。

 X will evaluate to V。 always， it's immutable。 It's always going to evaluate to them。

If you like to think about things less in terms of math and more in terms of like what's going on with the hardware under the hood。

 what's really happening here is we're getting a new memory location。

 we're going to name that location X， and we're going to store the value of V at it。😡。

Or I put that in terms of humans。 Really， it's the machine is going to do this。

 The machine is going to allocate a new memory location。

Use the name X for it and store the value V in it。As for the let definition itself。

 it does not count as an expression， so you cannot use let x equal E as a sub expressionpression of something else in UtahT。

 for example， you could not say let Z equal1。😡。

![](img/a64e124fc0ddcf54101d1d0a1a4c26d1_5.png)

Plus2。Okay， the let Z equals one is a definition。It binds a value to a name。

 It does not have a value itself。You are not allowed to use it in a context in which a value is expected。

 which is to say as an expression， so you try to compile that。

 you're going to get a syntax error here， it's saying an operator was expected。

 it doesn't understand how to parse that let definition when you've used it as an expression。



![](img/a64e124fc0ddcf54101d1d0a1a4c26d1_7.png)

If you do want to be able to use aette definition as an expression。

 there is a way to do that and we will see it next。



![](img/a64e124fc0ddcf54101d1d0a1a4c26d1_9.png)