# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P187：-187-SimPL Type Checker Part 1 Chap9 Video 34.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next up， we should actually implement pipe checkingck。

So type checking goes in the chain here between parsing and evaluation。

After we parse and get an AST out， we're going to type check that AST before we go ahead with evaluation。

So I've added type checking to the pipeline here， of course。

 now I need to actually write a type checking function。Okay。

 so I've started off implementing the type checking function here by writing the specification for it。

 T checking is just going to be E if E type checks successfully。In other words。

 it's just going to return its argument。As long as it's possible to give that argument of type。😡。

And more particularly what that means is that in the empty static environment。

 there must exist a type T such that E has type T。Type check is going to raise failure with some unspecified string if E does not type check。

So to implement Ty check， we're going to need to implement that typing relation。😡。

Let's do that with a function called type of。😡，Okay， let's pause here。

I've created a function type of and the spec for that function is that type of end E is the type of E in environment N。

That is， it's the T such that M shows that E has type T。

So think of the input of this function as everything to the left of the colon in the typing judgment and the output of the function as everything to the right of the colon in the typing judgment。

Now to use that function type of as part of type check， I need to call type of on the expression E。

In the empty environment。Now for environments I have a choice of how to implement them。

 obviously they are maps from identifiers to names。

 and the easiest implementation of map is either going to be as an association list or using the standard libraries built in Ma Funter。

😡，Let's play it easy here and use association Ls。😡，Of course。

 the empty list then is the empty environment。Let's return to the spec of type check。

It's supposed to return the expression E right now it's not doing that。

 it's returning the type of that expression， that's what type of returns。So we need to fix that。

So we'll compute the type of the expression。And then return that expression。

 assuming weve got to type back。Now， what should Ty of do if it doesn't manage to find a type。

 let's say that it will also raise failure。So that actually means from the perspective of type check we don't care what that type T is All we care about is that type of succeeds without raising an exception。

If it does succeed， we're going to just throw away that type， in fact。

 you can see the yellow underline there， that's a value T that is never used in the rest of that function。

So I could write， let underscore equal type of empty to solve that problem to get rid of that warning。

 or I could do this。That is， I could ignore the result of type checking。

 just run it for its side effects for raising an exception and then return E。

Let's start implementing typey of。Okay， let's pause here。

 having just implemented one branch of it so far。If the expression E is a Boolean constant。

 either true or false， then its type must be T bool。 That's what our type checking rule said。

So we'll return to Google for that。At this point， it's clear I could use the function syntactic sugar。

Next， I need to implement all the other type checking rules， let's do them a few at a time。😡。

We know that integer constants will have type T int。And we know that when we find a variable name。

 we're supposed to look it up in the static and environment and return whatever we find there。😡。

If we don't find a binding for that variable name， then we have an unbound variable error。

 and that's a type checking error at this point。😡，So we need to implement that。

Let's push this off into a helper function for looking at variables in an environment。

So I've implemented my helper function for Lookup now in terms of a function from the standard library。

I will raise an unbound variable error if the variable name is not bound in that。

Back down here in type of， of course， I need to change that variable name to X There are now two places in this interpreter where unbound variable error is getting raised。

One of them is during type checking。And the other is during evaluation。Now， during type checking。

 we're going to reject any program that would have an unbound variable error。

 but we still have to have this pattern match case down here in the evaluator because at runtime。

 it is a theoretical possibility from OAl's perspective that there could be an unbound variable error just because there could be a var constructor here。

We know， though， that we're never going to reach this point because of type checking。Nonetheless。

 we have to have this branch in the pattern match here， otherwise it would be inexhausive。

So we leave it in。Knowing that type checking will prevent it。

I'm going to introduce two new exception types so that I can disambiguate whether I get this exception for unboundone variables at runtime that is during EVval or at compile time that is during type checking。

😡，So I've added two new exception constructors and two convenience functions for raising both of those。

Now I can go through the rest of my code and disambiguate whether I'm getting a type checking error or a runtime error Now is this strictly necessary。

 no， of course not， I could have done all of this just by raising failure。

 but this helps make it a little clearer what the errors are that's resulting from my interpreter。😡。



![](img/1f40d215f8f6ed89022596463d32cced_1.png)

Okay， so having finished up patching up all of those， now I can return to implementing type of。Okay。

 let's pause here。I know that my implementation of the binary operator type checking rule is going to be more than just a very short line of code。

 so I've gone ahead and factored out a mutually recursive helper function for it。

 as we had been doing for implementation of evaluation before。

Here I want to match against the binary operator and the results of recursively type checking the sub expressionpressions E1 and E2 in order to figure out whether the application of that operator is correct。

😡，So to type check a binary operator， there's only three of them add mut and less than or equal to each one of those has to take two integers as its arguments and returns the appropriate type。

 an integer for add andmt and a bo for less than or equal to be off error is this error message that I've defined up here above already which is the operator and type mismatch again。

 that is something that could occur at type checking time and if so we'll catch it here and make sure that we raise an exception and never allow the rest of the program to be evaluated but down here as part of the evaluation it is also a possibility that it could occur at runtime Now in theory our type checker will prevent this but O Camel in order for its pattern match exhaustiveness checker to be satisfied is going to need to have a branch here and so here we'll raise a runtime error for that binary operator。



![](img/1f40d215f8f6ed89022596463d32cced_3.png)