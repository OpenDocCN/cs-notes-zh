# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P15：-015-Function Application Chap2 Video 10.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/dd5241583803548ad7a67e49e49b590b_0.png)

Function application。Is written。Just by putting expressions next to each other， juxtaposing them。

So if you want to apply a function to N different arguments。You write E0。

 which is the expression for the function and then and other expressions E1 through EN。

 and there's no parentheses required， no punctuation required unless you need to force a particular order of evaluation。

 say with arithmetic or making sure Ocaml is just parsing things the way you want them to be parsed。

Okay so get out of the habit of writing parentheses around the arguments to a function。

 you don't need them， and in fact， Oamel may not even understand what you're trying to do if you add them in。

😡，Especially if you start adding commas between the function arguments。

 notice there are no commas here。 it's actually incorrect to add them。

Evaluation of a function application proceeds as follows。First。

 evaluate all of the sub expressions to values， so evaluate E0 to evaluate。

 evaluate E1 to evaluate up to E。Now， after that's done。

 E0 needs to have evaluated to evaluate v0 that is a function。😡，It has to be a function。

 we can write it as an anonymous function here， we don't need its name right now。

Fun X1 through X in LOE。Now that we have that function。

 we can substitute the values of the arguments。For those names inside of the body of the function。

So substitute v1 for x1， substitute v2 for x2， and so forth。Inside that body expression E。

That's going to get us a new expression E prime that may have changed because we did some substitution inside of it。

Finish by evaluating E prime to evaluate V。😡，That value V is the result of the entire function application。

Let's do an example of that。

![](img/dd5241583803548ad7a67e49e49b590b_2.png)

Let's apply the anonymous function that increments its argument。To the expression 2 plus 3。Of course。

 if we increment  two plus three， we ought to get six， hopefully that's what we get in the end。



![](img/dd5241583803548ad7a67e49e49b590b_4.png)

What do our evaluation rules say Well， first evaluate E0 to a。



![](img/dd5241583803548ad7a67e49e49b590b_6.png)

Done already done because fund X0 x plus1 is an anonymous function and therefore is already a value。

 there's nothing to be done with it。Also， evaluate the arguments to values。

 So that means evaluating 2 plus 3， which of course， is going to give us5。

So what do we end up with next， we're trying to apply fun x0 x plus1 to5。



![](img/dd5241583803548ad7a67e49e49b590b_8.png)

Next step in function application， substitute the argument values for the names of the parameters。



![](img/dd5241583803548ad7a67e49e49b590b_10.png)

So I want to substitute 5 for x inside of the body of the anonymous function。That gives me5 plus one。

That is my expression E prime that the evaluation rules are referring to。Finally。

 evaluate E prime to a value5 plus1 evaluates to the value 6。

 and that is the result of the entire function application expression。Let's try a second example。

Suppose we apply the anonymous function that subtracts its second argument from its first。

To two other expressions。Okay， what did this a function application rule say？First。

 evaluate all the subexpressions。Done with the first one because it's already a value that anonymous function is already a value。



![](img/dd5241583803548ad7a67e49e49b590b_12.png)

Evaluate the second one。And the third sub expression。 So three times 1。

 What is that evaluate 2 that evaluates to 3，3-1 that evaluates to 2。

Now we can substitute each of those values for the name inside of the body， so we've got x minus y。

 and we substitute3 for x。And two for y。That's our sub expressionion E prime as the result of the substitution。

And finish by evaluating that to a value 3-2 evaluates to the value 1。



![](img/dd5241583803548ad7a67e49e49b590b_14.png)