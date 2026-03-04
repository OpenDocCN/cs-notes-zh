# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p130 32_07_implementing-closures -BV1bw4m1D7MM_p130-

So at the end of the previous segment I said that was everything you needed to know about environments。

 and I realized that's not entirely true。 the most interesting part of your homework assignment。

 the most interesting part of many programming languages is implementing closures and I want to show you how to do that。

 I hope you really enjoy this because I think it's the most interesting and mindbending part of what we do in this part of the course and that's that the language is going to have firstclass closures so you're gonna be able to write map and filter and call them with closures we're going to implement lexical scope of course because that's the appropriate semantics and we need to learn how to do that。



![](img/68d9aaeb13b6b8951d6160cc9420792d_1.png)

Fortunately， what you have to implement is what we have been stressing。How closures work。

 I just need to tell you a little bit about how to code them up and again the strategy here is I'm just going to do this in English and in PowerPoint and be your job to translate the ideas into the racket code you're using to write your interpreter。



![](img/68d9aaeb13b6b8951d6160cc9420792d_3.png)

So the magic question is this。We know， thanks to lexical scope。

 that when we evaluate a function body， we use the environment where the function was defined。

 extended to map the argument to the actual result。

So how are we going to have that environment around？Our interpreter only takes as an argument。

 the current environment。 It does not take as an argument。

 the environment where the function was defined。So here is the trick， if you will。

 The lack of magic is when we define a function， we will create a closure that includes the environment。

😊，So later， when we use that closure， we have the environment stored away and we can use it appropriately。

So when we have our language definition， we have all thestructs that programmers use to write their programs。

And then we'll have one more， one that they should not use in their source programs。

 you can use it for testing things out if you like， and that's thestruct closure and has two parts。

 Yes， it has the function that's going to include the argument and the body for the code and all the code parts of the closure。

 but then we also store the environment。So here's what happens。A closure is a value。

 So like all values， if you have a closure， your interpreter should just return it。But a function。

Is not quite a value。We often say that functions are values。

 but really closures our values When you go to interpret a function。You have the current environment。

 you have this function， make a closure out of both of them。

So now you return that and this closure carries with it。

 its own environment that we will use later when we use the closure。

So that is how you interpret functions。 The only other thing I have to tell you is how to interpret a function call。

 right， So now we handle the function case of our interpreter。

 Now what happens when you actually do a call。 So let's do that。 And that's all there is to it。



![](img/68d9aaeb13b6b8951d6160cc9420792d_5.png)

Suppose you add something like call of expression 1 and expression 2。

So expression one should evaluate to some closure， expression two should evaluate to some argument。

 we should call the closure with the argument。Okay， so the first thing we need to do。

 like many things where we have sub expressionions is evaluate them。

 So use the current environment to evaluate E1 to a closure。

It's an error if you don't get a closure back because I would be trying to like treat a number as a function or something like that and use the current environment to evaluate E2 to a。

 just normal recursion so far。Now we have a closure and an argument。😡。

What we need to do next is evaluate the closures functions body。Using not the current environment。

But the closures environment， the other thing that is stored in the closure。

We're going to start with that environment， then we'll extend it to map the functions argument name to the value we have。

 the result of evaluating E2。And the way we're going to deal with recursion on the homework assignment because our functions can be recursive is we'll go ahead and further extend the environment for the purpose of recursion to map the function's name to the entire closure。

 not just to a function， but to the entire closure， because we still need that current environment。

So that way， when we go to evaluate the closures functions body。

 any variables we look up will either be the function argument。

 and that will be mapped to the right thing。Or we'll use the environment back when the function was defined。

And the only thing left is this little workaround for recursion。

 if inside that function's body you want to recursively call the function。

 you should use the same closure， and so that's why we'll map the functions name for the purpose of recursion to the entire closure。

That's what you need to do rather than just thinking of it as let's take what Dan said and try to code that up。

 even though I don't understand it， I encourage you to actually understand it to appreciate that this is the same semantics we learned a few weeks ago back when we learned closures I told you that a closure was a pair。

Well， the struct foreclosure has two fields。 That's like a pair。 There's the code part。

 and there's the environment part。 And the reason why closures are not magic is when we create a closure。

 we store the environment。 And then when we use a closure。

 we use that environment for evaluating the function's body。😊，Notice that given a closure。

 that is the only environment we will ever use to evaluate that function's body with that closure。

 but every time we evaluate a function definition， a function that gets returned。

 we create a new closure using whatever environment was current back when we evaluated that function。

And that is the quote unquote magic of implementing higher order functions。

 once you implement it in your programming language， you'll be able to use higher order functions。

 closures， variables that are did not defined in function bodies。

 and all the wonderful other things we've been studying with closures in our functional programming languages。



![](img/68d9aaeb13b6b8951d6160cc9420792d_7.png)