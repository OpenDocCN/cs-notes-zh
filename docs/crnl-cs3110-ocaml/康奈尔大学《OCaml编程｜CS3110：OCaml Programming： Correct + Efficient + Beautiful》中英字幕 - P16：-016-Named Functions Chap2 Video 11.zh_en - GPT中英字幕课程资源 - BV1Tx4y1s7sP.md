# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P16：-016-Named Functions Chap2 Video 11.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Anonymous functions are great， but we're not going to get very far in our programmingtu main lives if we have to leave everything without a name。

Let's see how to give names to functions。Actually， it's really no different from what we've seen before for giving names to other values。

 We've already seen that I could say let x equal 31，10， for example。

You can do the same with functions because anonymous functions are values。

 So suppose I had my increment function。 Remember that was fun X， arrow X plus1。

I could give a name to that。 I could bind it to a name by sign saying， let ink equal。And then。

 that function value。And now I have a function named ink， whose type is int arrow int。And， in fact。

 will increment any argument that I pass to it。Now。

 having to write the fun X arrow is not always going to be fun， really。

 it's a lot of additional syntax。 So Ocal lets us simplify this kind of function definition by instead writing let ink and then putting the argument in there without having to write the fun keyword。

 So let ink X equal X plus1。Means the same thing as what we wrote a couple lines above。

Just another way of writing the functions syntactically， it'll do the same thing。O。

So I was able to get rid of the fun keyword and the arrow by putting the argument on the left hand side of the equals sign。

Let's also rewrite our average function。The average of two numbers， X and Y。X plus dot y divide by 2。

And now I can take the average of two numbers。Of course。

 I could have written that with anonymous function syntax as well。

The anonymous function that takes in x and Y and returns their average。

But that does involve a fair amount of extra typing。

 And so most oamml programmers would not write it that way。

 They would just use the more convenient form that puts the arguments to the left of the equals s。

We've now seen two pieces of code that are syntactically different， but semantically equivalent。

Let ink equal fun X arrow X plus1 is syntactically different from let ink X equal x plus 1。

 but they mean the same thing。 They evaluate the same way。

This phenomenon is known as syntactic sugar。 When there's two different ways of writing something syntactically in a language。

 They mean the same thing， but one of thems a little easier to use。 In fact。

 you could get away without having one of them， but your life would be a little less sweet without it。

The first form with the fun key word is the more primitive form， but it's not as sweet。

The second form where we put the argument on the left is a little sweeter。

 It's a little nicer to write。 We could get away without it。

 but isn't it nice that the language has it for us instead。

Syntactic sugar is something we're going to see a lot of because Ocal is designed in a way such that more complicated kinds of expressions in the language can actually be reduced to simpler kinds。

Here's another example of this。Fund X 0 x plus 1， applied to 2。

Is syntactically different from the next line。 Let x equal 2 in x plus1。

But they are semantically equivalent。If that's not apparent。

 take a moment and go back to the evaluation rules for each of those。

 What do the evaluation rules say for the anonymous function application。

 They say to substitute the argument too for the name X inside of the body expression。

That yields 2 plus1。What do the evaluation rules for lead expressions say？

Substitute the binding expression for the variable name inside of the body。

That means substituting 2 for x， yielding 2 plus 1。Either way， the same substitution occurs。

 the same computation occurs。So the lead expression is really syntactic sugar。

It's a little nicer than having to write function application with an anonymous function。

 but you could technically get away without having it in the language。Having it there， though。

 makes the language a little sweeter。

![](img/34710b95c3ef7f93c067de63ff8f04d9_1.png)

Let's take another look at one of the examples we saw before。

 earlier we looked at an anonymous function applied to some arguments。

 supposeose you had instead defined that anonymous function at the top level in UT as let Fxy equal x minus y。

And then applied F to the arguments 3 and2。 I've already gone ahead and simplified them from the arguments that we used before。

Well， now we know a lot about syntactic sugar and evaluation rules。

 and so we can explain a little more carefully how this code is evaluated。First off。

 we know that when we write let definitions in the top level。

 they are really understood as nested let expressions。So those two separate definitions， well。

 the first definition followed by the second expression， actually work together in this way。

 let f X y equal x minus y in f applied to 3 and 2。We now know that the let expression itself。

When we bind F to this function is using syntactic sugar， that's really fun。 X， Y， arrow， X minus Y。

And we know from the evaluation rules of let expressions。That that means replacing F。

By the anonymous function。 So now we have。F 3，2， where I replace F。Byhy that whole subexpression。

And from the evaluation rules of anonymous function application。

 we know that means taking the body x minus y， replacing x with 3 and y with 2。

With a final result of one。So now you know in Utah， when you're typing， let F X， Y。Equal x minus y。

 and then applying f to 3 and 2。 those are the evaluation rules that are actually going on behind the scenes to produce that final value of one。



![](img/34710b95c3ef7f93c067de63ff8f04d9_3.png)