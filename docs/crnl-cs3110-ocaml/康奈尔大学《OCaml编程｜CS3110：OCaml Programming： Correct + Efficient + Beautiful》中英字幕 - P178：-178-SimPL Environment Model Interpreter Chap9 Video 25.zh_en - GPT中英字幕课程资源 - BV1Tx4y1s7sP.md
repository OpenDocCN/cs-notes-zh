# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P178：-178-SimPL Environment Model Interpreter Chap9 Video 25.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's see how to implement an interpreter for simple using this big step environment model。The Leer。

 the parser， the AST， those all stay the same as everything we've done before。

It's just the evaluation that changes。 I have the completed interpreter here。

 Let's read through it together。First， I'm going to have dynamic environments。

 I'm using the standard library's map function to create that。

 This will be something that maps a string to a value。😡，The empty environment is， of course。

 just the empty value from inside of module end that I've created here， and for convenience。

 I will define the type end here to be something that is an environment dot T that is the representation type of that map。

😡，Prameterterized on value。 So it's going to map strings to values。

Where value here is going to be a new type that I'm defining。

 which represents a value in this language。 Now this is different from the implementation we had before。

 where everything was just an expert In fact， you might remember that once upon a time I got a little bit frustrated with the fact that everything was an expert because it meant that I had to have a catch all case in a pattern match。

😡，Now we're going to introduce a type for values。 So this will represent a value in the language simple。

 and there are only two kinds of values in that language， int and bo。

I want to have constructors for each of those， but if I used int and Bool as the constructor names。

 that of course would clash with the names inside of the AST where I already have int and bo as expressions。

😡。

![](img/9b599d53fe0e2a14319db8f56afaf5ce_1.png)

So I am going to precede each of those with V， so why we'll have V int for values that are integers and V bo for values that are bos。

😡，I have my usual error messages here。And now we get to the evaluation function。

So it takes a new argument now， which is the dynamic environment end。

And it returns not an expression， but a value。And it does that by matching the input expression against the syntactic form from the AST and using the semantics that we just defined on the slides to implement evaluation。

So an integer evaluates to that same integer， but as a V end because it's now represented as a value。

A bool bee evaluates to V bool be in the same way。For a variable x。

 we're going to use a helper function。That's going to implement looking up that variable inside of the environment。

If it's not found in the environment that will raise an unbound variable error， Otherwise。

 it's going to return the value to which the variable is bounded。For binary operators。

 much like we had done before， we'll evaluate E1 and E2， both in this current dynamic environment。

 and then return the appropriate value for each one of those。

 assuming that all of the types work out correctly for the operators。😡，For let expressions。

 we'll go ahead and evaluate the binding expression E1 to evaluate V1。

We'll then add a binding of x to V1 in the dynamic environment that creates a new dynamic environment and prime。

And we'll finish by evaluating E2 inside of that new dynamic environment。

For if well evaluate the guard E1 to a value and then we'll match against that value。 If it's true。

 we'll evaluate E2。 If it's false， we'll evaluate E3。

 Anything else we've got an error with the guard。Finally。

 the string of vowel function needs to be updated。 Now we can get rid of that catch all case。

 We can match V， which must be a value against either V in or V bool and convert it to the appropriate string。

And that's all there is to it。 It's really quite straightforward and pleasant to implement an environment model interpreter in this way。



![](img/9b599d53fe0e2a14319db8f56afaf5ce_3.png)